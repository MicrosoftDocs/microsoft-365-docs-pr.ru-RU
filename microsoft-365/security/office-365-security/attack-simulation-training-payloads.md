---
title: Создание полезной нагрузки для обучения моделированию атак
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут научиться создавать пользовательские полезной нагрузки для обучения моделированию атак в Microsoft Defender для Office 365.
ms.openlocfilehash: 45311ad4c4eb09c8238d278475248680fbc66287
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877133"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="14bae-103">Создание пользовательских полезных данных для обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="14bae-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="14bae-104">Корпорация Майкрософт предлагает надежный каталог полезной нагрузки для различных методов социальной инженерии для сопряжения с обучением моделированию атак.</span><span class="sxs-lookup"><span data-stu-id="14bae-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="14bae-105">Однако может потребоваться создать пользовательские полезной нагрузки, которые будут лучше работать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="14bae-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="14bae-106">В этой статье описывается создание полезной нагрузки в обучении моделированию атак в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="14bae-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="14bae-107">Для создания полезной нагрузки нажмите кнопку **"Создать** полезное" на выделенной вкладке [ **"Payloads"**](https://security.microsoft.com/attacksimulator?viewid=payload) или в мастере [создания имитации.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="14bae-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="14bae-108">На первом этапе мастера будет выбран тип полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="14bae-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="14bae-109">**В настоящее время доступна только электронная почта.**</span><span class="sxs-lookup"><span data-stu-id="14bae-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="14bae-110">Затем выберите связанный метод.</span><span class="sxs-lookup"><span data-stu-id="14bae-110">Next, select an associated technique.</span></span> <span data-ttu-id="14bae-111">Дополнительные сведения о методах см. в [теме "Выбор метода социальной инженерии".](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="14bae-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="14bae-112">На следующем этапе назовите полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="14bae-112">In the next step name your payload.</span></span> <span data-ttu-id="14bae-113">При желании вы можете дать ему описание.</span><span class="sxs-lookup"><span data-stu-id="14bae-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="14bae-114">Настройка полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="14bae-114">Configure payload</span></span>

<span data-ttu-id="14bae-115">Теперь пора создавать свои полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="14bae-115">Now it's time to build your payload.</span></span> <span data-ttu-id="14bae-116">В разделе сведений об отправителю ввести имя, адрес электронной почты и тему **сообщения.**</span><span class="sxs-lookup"><span data-stu-id="14bae-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="14bae-117">Выберите фишинговый URL-адрес из предоставленного списка.</span><span class="sxs-lookup"><span data-stu-id="14bae-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="14bae-118">Этот URL-адрес позже будет внедрен в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="14bae-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="14bae-119">Вы можете выбрать внутреннее сообщение электронной почты для отправитель ваших полезной нагрузки, которое сделает полезной нагрузки от другого сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="14bae-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="14bae-120">Это повышает подверженность полезной нагрузке и помогает информировать сотрудников о риске внутренних угроз.</span><span class="sxs-lookup"><span data-stu-id="14bae-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="14bae-121">Для создания полезной нагрузки доступен редактор с ХФ-текстом.</span><span class="sxs-lookup"><span data-stu-id="14bae-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="14bae-122">Вы также можете импортировать сообщение электронной почты, созданное заранее.</span><span class="sxs-lookup"><span data-stu-id="14bae-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="14bae-123">При создании тела сообщения электронной почты  вы можете использовать динамические теги для персонализации электронной почты в целевых адресах.</span><span class="sxs-lookup"><span data-stu-id="14bae-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="14bae-124">Щелкните **фишинговую ссылку,** чтобы добавить ранее выбранный URL-адрес фишинга в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="14bae-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Фишинговая ссылка и динамические теги, выделенные при создании полезной нагрузки для Microsoft Defender для Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="14bae-126">Чтобы сэкономить время, загляайте в параметре замены всех ссылок в сообщении электронной почты **на фишинговую ссылку.**</span><span class="sxs-lookup"><span data-stu-id="14bae-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="14bae-127">После создания полезной нагрузки нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="14bae-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="14bae-128">Добавление индикаторов</span><span class="sxs-lookup"><span data-stu-id="14bae-128">Adding indicators</span></span>

<span data-ttu-id="14bae-129">Индикаторы помогут сотрудникам, которые проходят моделирование атаки, понять, на что они могут смотреть в будущих атаках.</span><span class="sxs-lookup"><span data-stu-id="14bae-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="14bae-130">Чтобы начать, нажмите **кнопку "Добавить индикатор".**</span><span class="sxs-lookup"><span data-stu-id="14bae-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="14bae-131">Выберите индикатор, который вы хотите использовать, в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="14bae-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="14bae-132">Этот список содержит наиболее распространенные подсказки, которые отображаются в фишинговых сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="14bae-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="14bae-133">После выбора убедитесь, что для  размещения индикатора установлено положение "Из текста сообщения" и нажмите кнопку **"Выбрать текст".**</span><span class="sxs-lookup"><span data-stu-id="14bae-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="14bae-134">Выделите часть полезной нагрузки, в которой отображается этот индикатор, и нажмите кнопку **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="14bae-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Выделенное текст в тексте сообщения для добавления к индикатору в обучении моделированию атаки](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="14bae-136">Добавьте пользовательское описание для описания индикатора и щелкните в кадре предварительного просмотра индикатора, чтобы просмотреть индикатор.</span><span class="sxs-lookup"><span data-stu-id="14bae-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="14bae-137">После этого нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="14bae-137">Once done, click **Add**.</span></span> <span data-ttu-id="14bae-138">Повторите эти действия, пока не охватите все индикаторы в полезной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="14bae-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="14bae-139">Просмотр полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="14bae-139">Review payload</span></span>

<span data-ttu-id="14bae-140">Вы закончили создание полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="14bae-140">You're done building your payload.</span></span> <span data-ttu-id="14bae-141">Теперь пора просмотреть сведения и просмотреть предварительный просмотр полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="14bae-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="14bae-142">Предварительный просмотр будет включать все созданные индикаторы.</span><span class="sxs-lookup"><span data-stu-id="14bae-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="14bae-143">На этом этапе можно изменить каждую часть полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="14bae-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="14bae-144">После этого отправьте **свои** данные.</span><span class="sxs-lookup"><span data-stu-id="14bae-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14bae-145">В качестве источника созданных вами полезной нагрузки **будет** клиент.</span><span class="sxs-lookup"><span data-stu-id="14bae-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="14bae-146">При выборе полезной нагрузки убедитесь, что вы не фильтруете **клиент.**</span><span class="sxs-lookup"><span data-stu-id="14bae-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="14bae-147">См. также</span><span class="sxs-lookup"><span data-stu-id="14bae-147">Related links</span></span>

[<span data-ttu-id="14bae-148">Начало использования обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="14bae-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="14bae-149">Создание имитации фишинговой атаки</span><span class="sxs-lookup"><span data-stu-id="14bae-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="14bae-150">Получение аналитики с помощью обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="14bae-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
