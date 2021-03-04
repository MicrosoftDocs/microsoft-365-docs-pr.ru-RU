---
title: Предотвращение потери данных
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
description: Узнайте, как управлять настройками политик предотвращения потери данных.
ms.openlocfilehash: 54cd508ef0b0cfcf8b71dc86a4903f77a5354c36
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422067"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="cef94-103">Предотвращение потери данных с помощью DLP</span><span class="sxs-lookup"><span data-stu-id="cef94-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="cef94-104">Политики предотвращения потери данных помогают выявлять и защищать конфиденциальные сведения вашего бизнеса, такие как номера социального страхования или медицинские записи.</span><span class="sxs-lookup"><span data-stu-id="cef94-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="cef94-105">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="cef94-105">Try it!</span></span>

1. <span data-ttu-id="cef94-106">Чтобы начать работу, перейдите в [центр администрирования](https://admin.microsoft.com)и выберите **установку**.</span><span class="sxs-lookup"><span data-stu-id="cef94-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="cef94-107">Прокрутите **вниз, чтобы настроить предотвращение** потери данных, а затем выберите **Просмотр** и **управление**.</span><span class="sxs-lookup"><span data-stu-id="cef94-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="cef94-108">Чтобы изменить политику, выберите ее, выберите **политику Редактирование,** а затем выберите, что изменить.</span><span class="sxs-lookup"><span data-stu-id="cef94-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="cef94-109">Например, выберите **Расположения,** чтобы изменить то, что проверяется.</span><span class="sxs-lookup"><span data-stu-id="cef94-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="cef94-110">Чтобы включить сканирование контента в Microsoft Teams, включите переключатель переключателя на положение **"Включен",** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cef94-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="cef94-111">Чтобы изменить параметры политики, выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cef94-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="cef94-112">Необходимо установить отдельные правила, применимые к небольшому и большому объему обнаруженного конфиденциального контента.</span><span class="sxs-lookup"><span data-stu-id="cef94-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="cef94-113">Расширите правило низкого объема.</span><span class="sxs-lookup"><span data-stu-id="cef94-113">Expand your low volume rule.</span></span> <span data-ttu-id="cef94-114">Выберите **правило Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cef94-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="cef94-115">Просмотрите параметры и отрегулируете их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="cef94-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="cef94-116">Например, можно настроить текст электронной **почты** и **настроить текст подсказки политики.**</span><span class="sxs-lookup"><span data-stu-id="cef94-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="cef94-117">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cef94-117">Select **Save**.</span></span>
1. <span data-ttu-id="cef94-118">Повторите для правила высокой громкости.</span><span class="sxs-lookup"><span data-stu-id="cef94-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="cef94-119">Выберите **Сохранить,** а затем **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cef94-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="cef94-120">Чтобы создать новую политику, выберите **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="cef94-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="cef94-121">Можно создать настраиваемую политику или начать с шаблона.</span><span class="sxs-lookup"><span data-stu-id="cef94-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="cef94-122">Например, чтобы создать политику HIPAA,  выберите шаблон медицинских и медицинских учреждений, а затем выберите Закон США о медицинском страховании **(HIPAA).**</span><span class="sxs-lookup"><span data-stu-id="cef94-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="cef94-123">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-123">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-124">Введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="cef94-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="cef94-125">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-125">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-126">Выберите расположения для сканирования.</span><span class="sxs-lookup"><span data-stu-id="cef94-126">Choose the locations to scan.</span></span> <span data-ttu-id="cef94-127">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-127">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-128">Выберите тип контента, который необходимо защитить.</span><span class="sxs-lookup"><span data-stu-id="cef94-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="cef94-129">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-129">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-130">Выберите, что нужно сделать, если конфиденциальную информацию обнаружить.</span><span class="sxs-lookup"><span data-stu-id="cef94-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="cef94-131">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-131">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-132">Настройка доступа и переопределения разрешений.</span><span class="sxs-lookup"><span data-stu-id="cef94-132">Customize your access and override permissions.</span></span> <span data-ttu-id="cef94-133">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-133">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-134">Выберите, когда вы хотите, чтобы политика вступила в силу.</span><span class="sxs-lookup"><span data-stu-id="cef94-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="cef94-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cef94-135">Select **Next**.</span></span>
1. <span data-ttu-id="cef94-136">Просмотрите параметры и выберите **Create**.</span><span class="sxs-lookup"><span data-stu-id="cef94-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="cef94-137">После того, как политика вступает в силу, будет заблокировано сообщение электронной почты, содержающее описанные конфиденциальные сведения, и отправитель, попытавший отправить эту информацию, увидит предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="cef94-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>