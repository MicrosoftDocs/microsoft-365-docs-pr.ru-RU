---
title: Создание полезных данных для обучения по моделированию атак
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Узнайте, как создавать пользовательские полезные данные для обучения по моделированию атак в защитнике Майкрософт для Office 365.
ms.openlocfilehash: ffb5397d9b39a35b4cb8bd0fdb3301cd156896e1
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944596"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="19a7c-103">Создание настраиваемых полезных данных для обучения по моделированию атак</span><span class="sxs-lookup"><span data-stu-id="19a7c-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="19a7c-104">Корпорация Майкрософт предлагает надежный Каталог полезных данных для различных приемов социального проектирования, которые можно связать с обучением по моделированию атак.</span><span class="sxs-lookup"><span data-stu-id="19a7c-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="19a7c-105">Однако может потребоваться создать пользовательские полезные данные, которые будут лучше работать в Организации.</span><span class="sxs-lookup"><span data-stu-id="19a7c-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="19a7c-106">Ниже описано, как создать полезную нагрузку при моделировании атак через защитник Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="19a7c-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="19a7c-107">Вы можете создать полезную нагрузку, нажав кнопку **создать полезную нагрузку** на [вкладке выделенные **полезные данные**](https://security.microsoft.com/attacksimulator?viewid=payload) или в [мастере создания моделей](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="19a7c-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="19a7c-108">На первом шаге мастера будет выбран тип полезных данных.</span><span class="sxs-lookup"><span data-stu-id="19a7c-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="19a7c-109">**В настоящее время доступна только электронная почта**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-109">**Currently only email is available**.</span></span>

<span data-ttu-id="19a7c-110">Затем выберите связанный метод.</span><span class="sxs-lookup"><span data-stu-id="19a7c-110">Next, select an associated technique.</span></span> <span data-ttu-id="19a7c-111">Более подробную информацию о методах можно узнать на странице [Выбор метода социального проектирования](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="19a7c-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="19a7c-112">На следующем шаге Назовите свои полезные данные.</span><span class="sxs-lookup"><span data-stu-id="19a7c-112">In the next step name your payload.</span></span> <span data-ttu-id="19a7c-113">При необходимости можно присвоить ему описание.</span><span class="sxs-lookup"><span data-stu-id="19a7c-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="19a7c-114">Настройка полезных данных</span><span class="sxs-lookup"><span data-stu-id="19a7c-114">Configure payload</span></span>

<span data-ttu-id="19a7c-115">Теперь нужно создать свои полезные данные.</span><span class="sxs-lookup"><span data-stu-id="19a7c-115">Now it's time to build your payload.</span></span> <span data-ttu-id="19a7c-116">Введите имя отправителя, адрес электронной почты и тему сообщения электронной почты в разделе **сведения о отправителю** .</span><span class="sxs-lookup"><span data-stu-id="19a7c-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="19a7c-117">Выберите из предоставленного списка URL-адрес фишинга.</span><span class="sxs-lookup"><span data-stu-id="19a7c-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="19a7c-118">Этот URL-адрес позже будет внедрен в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="19a7c-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="19a7c-119">Вы можете выбрать внутреннюю электронную почту для отправителя полезных данных, чтобы они отображались как поступающие от другого сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="19a7c-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="19a7c-120">Это увеличит сусцептибилити до полезных данных и поможет проинструктировать сотрудников о риске внутренних угроз.</span><span class="sxs-lookup"><span data-stu-id="19a7c-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="19a7c-121">Для создания полезных данных можно использовать редактор форматированного текста.</span><span class="sxs-lookup"><span data-stu-id="19a7c-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="19a7c-122">Вы также можете импортировать электронную почту, которую вы создали заранее.</span><span class="sxs-lookup"><span data-stu-id="19a7c-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="19a7c-123">При структурировании текста сообщения электронной почты воспользуйтесь преимуществами **динамических тегов** , чтобы настроить электронное письмо для целей.</span><span class="sxs-lookup"><span data-stu-id="19a7c-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="19a7c-124">Щелкните **ссылку фишинга** , чтобы добавить ранее выбранный URL-адрес фишинга в текст сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="19a7c-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![Ссылка фишинга и динамические теги, выделенные в создании полезных данных для защитника Майкрософт для Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="19a7c-126">Чтобы сохранить данные в некоторый момент времени, включите параметр, чтобы **заменить все ссылки в сообщении электронной почты на поддельные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="19a7c-127">Завершив создание полезных данных, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="19a7c-128">Добавление индикаторов</span><span class="sxs-lookup"><span data-stu-id="19a7c-128">Adding indicators</span></span>

<span data-ttu-id="19a7c-129">Индикаторы помогут сотрудникам, проходящим через моделирование атак, понять, что они могут искать в следующих атаках.</span><span class="sxs-lookup"><span data-stu-id="19a7c-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="19a7c-130">Для запуска нажмите кнопку **добавить индикатор**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="19a7c-131">Выберите из раскрывающегося списка индикатор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="19a7c-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="19a7c-132">В этом списке содержатся наиболее распространенные пункты, которые появляются в сообщениях фишинга.</span><span class="sxs-lookup"><span data-stu-id="19a7c-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="19a7c-133">Выполнив выбранное значение, убедитесь, что в поле Расположение индикатора задано значение **из текста** сообщения и нажмите кнопку **выбрать текст**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="19a7c-134">Выделите часть полезных данных, в которой отображается этот индикатор, и нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Выделенный текст в тексте сообщения, который добавляется к индикатору в учебном курсе "моделирование атак"](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="19a7c-136">Добавьте настраиваемое описание для описания индикатора и щелкните в кадре предварительного просмотра индикатора, чтобы увидеть предварительный просмотр индикатора.</span><span class="sxs-lookup"><span data-stu-id="19a7c-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="19a7c-137">После этого нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="19a7c-137">Once done, click **Add**.</span></span> <span data-ttu-id="19a7c-138">Повторяйте эти действия, пока не перейдете все индикаторы в полезных данных.</span><span class="sxs-lookup"><span data-stu-id="19a7c-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="19a7c-139">Просмотр полезных данных</span><span class="sxs-lookup"><span data-stu-id="19a7c-139">Review payload</span></span>

<span data-ttu-id="19a7c-140">Создание полезных данных завершено.</span><span class="sxs-lookup"><span data-stu-id="19a7c-140">You're done building your payload.</span></span> <span data-ttu-id="19a7c-141">Теперь настало время просмотреть сведения и посмотреть предварительный просмотр полезных данных.</span><span class="sxs-lookup"><span data-stu-id="19a7c-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="19a7c-142">В предварительной версии будут включены все созданные вами индикаторы.</span><span class="sxs-lookup"><span data-stu-id="19a7c-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="19a7c-143">Вы можете редактировать каждую часть полезных данных на этом шаге.</span><span class="sxs-lookup"><span data-stu-id="19a7c-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="19a7c-144">После того как вы удовлетворены, **отправляйте** свои полезные данные.</span><span class="sxs-lookup"><span data-stu-id="19a7c-144">Once satisfied, **Submit** your payload.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="19a7c-145">В качестве источника создаваемых полезных данных будет задан **клиент** .</span><span class="sxs-lookup"><span data-stu-id="19a7c-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="19a7c-146">При выборе полезных данных убедитесь, что **клиент** не фильтруется.</span><span class="sxs-lookup"><span data-stu-id="19a7c-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>