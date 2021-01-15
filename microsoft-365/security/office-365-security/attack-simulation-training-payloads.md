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
ms.openlocfilehash: e3285b99d5b64255b9fdbda8c76b6f133aa013b2
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870867"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="3dd9c-103">Создание пользовательских полезных данных для обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="3dd9c-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="3dd9c-104">Корпорация Майкрософт предлагает надежный каталог полезной нагрузки для различных методов социальной инженерии для сопряжения с обучением моделированию атак.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="3dd9c-105">Однако может потребоваться создать пользовательские полезной нагрузки, которые будут лучше работать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="3dd9c-106">В этой статье описывается создание полезной нагрузки в обучении моделированию атак в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3dd9c-107">Для создания полезной нагрузки нажмите кнопку **"Создать** полезное" на выделенной вкладке ["Payloads"](https://security.microsoft.com/attacksimulator?viewid=payload) или в мастере [создания имитации.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="3dd9c-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="3dd9c-108">На первом этапе мастера будет выбран тип полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="3dd9c-109">**В настоящее время доступна только электронная почта.**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="3dd9c-110">Затем выберите связанный метод.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-110">Next, select an associated technique.</span></span> <span data-ttu-id="3dd9c-111">Дополнительные сведения о методах см. в [теме "Выбор метода социальной инженерии".](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="3dd9c-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="3dd9c-112">На следующем этапе назовите ваши полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-112">In the next step name your payload.</span></span> <span data-ttu-id="3dd9c-113">При желании вы можете дать ему описание.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="3dd9c-114">Настройка полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="3dd9c-114">Configure payload</span></span>

<span data-ttu-id="3dd9c-115">Теперь пора создавать свои полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-115">Now it's time to build your payload.</span></span> <span data-ttu-id="3dd9c-116">В разделе сведений об отправителю ввести имя, адрес электронной почты и тему **сообщения.**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="3dd9c-117">Выберите фишинговый URL-адрес из предоставленного списка.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="3dd9c-118">Этот URL-адрес позже будет внедрен в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="3dd9c-119">Вы можете выбрать внутреннее сообщение электронной почты для отправитель ваших полезной нагрузки, которое будет отображаться как отправленные другим сотрудником компании.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="3dd9c-120">Это повышает подверженность полезной нагрузке и помогает информировать сотрудников о риске внутренних угроз.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="3dd9c-121">Для создания полезной нагрузки доступен редактор с ОКБ.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="3dd9c-122">Вы также можете импортировать сообщение электронной почты, созданное заранее.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="3dd9c-123">При создании тела сообщения электронной почты  вы можете использовать динамические теги для персонализации электронной почты в целевых адресах.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="3dd9c-124">Щелкните **фишинговую ссылку,** чтобы добавить ранее выбранный URL-адрес фишинга в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Фишинговая ссылка и динамические теги, выделенные при создании полезной нагрузки для Microsoft Defender для Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="3dd9c-126">Чтобы сэкономить время, загляайте в параметре замены всех ссылок в сообщении электронной почты **на фишинговую ссылку.**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="3dd9c-127">После создания полезной нагрузки по своему желанию нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="3dd9c-128">Добавление индикаторов</span><span class="sxs-lookup"><span data-stu-id="3dd9c-128">Adding indicators</span></span>

<span data-ttu-id="3dd9c-129">Индикаторы помогут сотрудникам, которые проходят моделирование атаки, понять, на что они могут ходить в будущих атаках.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="3dd9c-130">Чтобы начать, нажмите **кнопку "Добавить индикатор".**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="3dd9c-131">Выберите индикатор, который вы хотите использовать, в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="3dd9c-132">Этот список содержит наиболее распространенные подсказки, которые отображаются в фишинговых сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="3dd9c-133">После выбора убедитесь, что для  размещения индикатора установлено положение "От текста сообщения" и нажмите кнопку **"Выбрать текст".**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="3dd9c-134">Выделите часть полезной нагрузки, в которой отображается этот индикатор, и нажмите кнопку **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Выделенное текст в тексте сообщения для добавления к индикатору в обучении моделированию атаки](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="3dd9c-136">Добавьте пользовательское описание для описания индикатора и щелкните в кадре предварительного просмотра индикатора, чтобы просмотреть индикатор.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="3dd9c-137">После этого нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-137">Once done, click **Add**.</span></span> <span data-ttu-id="3dd9c-138">Повторите эти действия, пока не закройте все индикаторы в полезной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="3dd9c-139">Просмотр полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="3dd9c-139">Review payload</span></span>

<span data-ttu-id="3dd9c-140">Вы закончили создание полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-140">You're done building your payload.</span></span> <span data-ttu-id="3dd9c-141">Теперь пора просмотреть сведения и просмотреть сведения о полезной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="3dd9c-142">Предварительный просмотр будет включать все созданные индикаторы.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="3dd9c-143">На этом этапе можно изменить каждую часть полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="3dd9c-144">После этого отправьте **свои** данные.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dd9c-145">Созданные вами полезной нагрузки будут иметь **клиент** в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="3dd9c-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="3dd9c-146">При выборе полезной нагрузки убедитесь, что вы не фильтруете **клиент.**</span><span class="sxs-lookup"><span data-stu-id="3dd9c-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="3dd9c-147">См. также</span><span class="sxs-lookup"><span data-stu-id="3dd9c-147">Related links</span></span>

[<span data-ttu-id="3dd9c-148">Начало работы с обучением моделированию атак</span><span class="sxs-lookup"><span data-stu-id="3dd9c-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="3dd9c-149">Создание имитации фишинговой атаки</span><span class="sxs-lookup"><span data-stu-id="3dd9c-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="3dd9c-150">Получение аналитики с помощью обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="3dd9c-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
