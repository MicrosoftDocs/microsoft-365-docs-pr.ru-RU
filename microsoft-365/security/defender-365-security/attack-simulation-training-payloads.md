---
title: Создание полезной нагрузки для обучения имитации атаки
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут узнать, как создавать настраиваемые рабочие нагрузки для обучения имитации атак в Microsoft Defender для Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073525"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="51082-103">Создание пользовательских полезных данных для обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="51082-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="51082-104">Корпорация Майкрософт предлагает надежный каталог полезной нагрузки для различных методов социальной инженерии в паре с обучением имитации атак.</span><span class="sxs-lookup"><span data-stu-id="51082-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="51082-105">Однако может потребоваться создать настраиваемые рабочие нагрузки, которые будут работать лучше для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="51082-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="51082-106">В этой статье описывается создание полезной нагрузки в обучении моделированию атак в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="51082-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="51082-107">Вы можете создать полезной нагрузки, нажав на **Создание** полезной нагрузки в выделенной вкладке [ **Полезной**](https://security.microsoft.com/attacksimulator?viewid=payload) нагрузки или в [мастере создания моделирования](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="51082-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="51082-108">На первом этапе мастера будет выбран тип полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51082-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="51082-109">**В настоящее время доступна только электронная почта.**</span><span class="sxs-lookup"><span data-stu-id="51082-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="51082-110">Далее выберите связанный метод.</span><span class="sxs-lookup"><span data-stu-id="51082-110">Next, select an associated technique.</span></span> <span data-ttu-id="51082-111">Дополнительные сведения о методах см. в [подборе метода социальной инженерии.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="51082-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="51082-112">На следующем шаге назовите полезной нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="51082-112">In the next step name your payload.</span></span> <span data-ttu-id="51082-113">Необязательно, вы можете дать ему описание.</span><span class="sxs-lookup"><span data-stu-id="51082-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="51082-114">Настройка полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="51082-114">Configure payload</span></span>

<span data-ttu-id="51082-115">Теперь пришло время для создания полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51082-115">Now it's time to build your payload.</span></span> <span data-ttu-id="51082-116">Ввод имени, адреса электронной почты и темы электронной почты в разделе **Сведения отправитель.**</span><span class="sxs-lookup"><span data-stu-id="51082-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="51082-117">Выберите URL-адрес фишинга из предоставленного списка.</span><span class="sxs-lookup"><span data-stu-id="51082-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="51082-118">Этот URL-адрес позже будет встроен в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="51082-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="51082-119">Вы можете выбрать внутреннюю электронную почту отправитель полезной нагрузки, которая будет отображаться как исходя из другого сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="51082-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="51082-120">Это увеличит восприимчивость к полезной нагрузке и поможет обучить сотрудников риску внутренних угроз.</span><span class="sxs-lookup"><span data-stu-id="51082-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="51082-121">Для создания полезной нагрузки доступен редактор с богатым текстом.</span><span class="sxs-lookup"><span data-stu-id="51082-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="51082-122">Вы также можете импортировать электронную почту, созданную заранее.</span><span class="sxs-lookup"><span data-stu-id="51082-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="51082-123">Создав тело электронной почты, вы  сможете использовать динамические теги для персонализации электронной почты в целевых адресах.</span><span class="sxs-lookup"><span data-stu-id="51082-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="51082-124">Щелкните **фишинговую** ссылку, чтобы добавить выбранный ранее URL-адрес фишинга в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="51082-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Фишинговые ссылки и динамические теги, выделенные в создании полезной нагрузки для Microsoft Defender для Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="51082-126">Чтобы сэкономить время, загляайте на возможность заменить все ссылки в сообщении электронной почты **ссылкой фишинга.**</span><span class="sxs-lookup"><span data-stu-id="51082-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="51082-127">После создания полезной нагрузки по своему вкусу нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="51082-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="51082-128">Добавление индикаторов</span><span class="sxs-lookup"><span data-stu-id="51082-128">Adding indicators</span></span>

<span data-ttu-id="51082-129">Индикаторы помогут сотрудникам, которые проходят моделирование атак, понять подсказки, которые они могут искать в будущих атаках.</span><span class="sxs-lookup"><span data-stu-id="51082-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="51082-130">Для начала нажмите **кнопку Добавить индикатор**.</span><span class="sxs-lookup"><span data-stu-id="51082-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="51082-131">Выберите индикатор, который вы хотите использовать из выпадаемого списка.</span><span class="sxs-lookup"><span data-stu-id="51082-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="51082-132">Этот список является куратором, чтобы содержать наиболее распространенные подсказки, которые отображаются в фишинговых сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="51082-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="51082-133">После выбора убедитесь, что размещение  индикатора установлено в тексте электронной почты и нажмите кнопку **Выберите текст**.</span><span class="sxs-lookup"><span data-stu-id="51082-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="51082-134">Выделите часть полезной нагрузки, в которой появится этот индикатор, и нажмите **кнопку Выберите**.</span><span class="sxs-lookup"><span data-stu-id="51082-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Выделен текст в теле сообщения, чтобы добавить к индикатору в обучении имитации атак](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="51082-136">Добавьте пользовательское описание для описания индикатора и нажмите кнопку в кадре предварительного просмотра индикатора, чтобы просмотреть индикатор.</span><span class="sxs-lookup"><span data-stu-id="51082-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="51082-137">После этого нажмите **кнопку Добавить**.</span><span class="sxs-lookup"><span data-stu-id="51082-137">Once done, click **Add**.</span></span> <span data-ttu-id="51082-138">Повторите эти действия, пока не охватите все индикаторы полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51082-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="51082-139">Просмотр полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="51082-139">Review payload</span></span>

<span data-ttu-id="51082-140">Вы закончили создание полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51082-140">You're done building your payload.</span></span> <span data-ttu-id="51082-141">Теперь пришло время просмотреть сведения и просмотреть сведения о полезной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="51082-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="51082-142">Предварительный просмотр будет включать все созданные индикаторы.</span><span class="sxs-lookup"><span data-stu-id="51082-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="51082-143">С этого шага можно изменить каждую часть полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51082-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="51082-144">После удовлетворены, вы можете **отправить** полезной нагрузки.</span><span class="sxs-lookup"><span data-stu-id="51082-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51082-145">Созданные вами полезной нагрузки будут иметь **клиента** в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="51082-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="51082-146">При выборе полезной нагрузки убедитесь, что вы не отфильтруете **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="51082-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="51082-147">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="51082-147">Related links</span></span>

[<span data-ttu-id="51082-148">Начало использования обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="51082-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="51082-149">Создание имитации фишинговых атак</span><span class="sxs-lookup"><span data-stu-id="51082-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="51082-150">Получение аналитики с помощью обучения имитации атаки</span><span class="sxs-lookup"><span data-stu-id="51082-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
