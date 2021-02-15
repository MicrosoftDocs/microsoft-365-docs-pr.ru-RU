---
title: Использование политик защиты от потери данных для облачных приложений, не в корпорации Майкрософт (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать политики DLP для облачных приложений, не в корпорации Майкрософт.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649660"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="8feea-103">Использование политик защиты от потери данных для облачных приложений, не в корпорации Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8feea-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="8feea-104">Политики защиты от потери данных (DLP) для облачных приложений, не в корпорации Майкрософт, являются частью набора функций защиты от потери данных Microsoft 365; с помощью этих функций вы можете обнаруживть и защищать конфиденциальные элементы в службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8feea-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="8feea-105">Дополнительные сведения обо всех предложениях защиты от потери данных (Майкрософт) см. в обзоре защиты [от потери данных.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="8feea-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="8feea-106">Политики DLP можно использовать для облачных приложений, не в корпорации Майкрософт, для отслеживания и обнаружения использования конфиденциальных элементов и их совместного использования через облачные приложения, не относящуюся к Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8feea-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="8feea-107">Использование этих политик обеспечивает видимость и контроль, необходимые для их правильного использования и защиты, а также помогает предотвратить рискованные действия, которые могут привести к их компрометации.</span><span class="sxs-lookup"><span data-stu-id="8feea-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8feea-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="8feea-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="8feea-109">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="8feea-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="8feea-110">Прежде чем приступить к использованию политик DLP в облачных приложениях, не в корпорации Майкрософт, подтвердите свою подписку [на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые надстройки.</span><span class="sxs-lookup"><span data-stu-id="8feea-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="8feea-111">Чтобы получить доступ к этой функции и использовать ее, необходимо иметь одну из этих подписок или надстройки:</span><span class="sxs-lookup"><span data-stu-id="8feea-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="8feea-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8feea-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="8feea-113">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8feea-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="8feea-114">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8feea-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="8feea-115">Подготовка среды Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8feea-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="8feea-116">Политики DLP для облачных приложений, не в корпорации Майкрософт, используют возможности cloud App Security DLP.</span><span class="sxs-lookup"><span data-stu-id="8feea-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="8feea-117">Чтобы использовать его, необходимо подготовить среду Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8feea-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="8feea-118">Инструкции см. в [настройках мгновенного видимости, защиты](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)и действий по управлению приложениями.</span><span class="sxs-lookup"><span data-stu-id="8feea-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="8feea-119">Подключение к облачному приложению от корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8feea-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="8feea-120">Чтобы использовать политику DLP для определенного облачного приложения от корпорации Майкрософт, приложение должно быть подключено к Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8feea-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="8feea-121">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="8feea-121">For information, see:</span></span>

- [<span data-ttu-id="8feea-122">Connect Box</span><span class="sxs-lookup"><span data-stu-id="8feea-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="8feea-123">Подключение Dropbox</span><span class="sxs-lookup"><span data-stu-id="8feea-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="8feea-124">Подключение G-Suite</span><span class="sxs-lookup"><span data-stu-id="8feea-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="8feea-125">Подключение Salesforce</span><span class="sxs-lookup"><span data-stu-id="8feea-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="8feea-126">Подключение Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="8feea-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="8feea-127">После подключения облачных приложений к Cloud App Security вы можете создать для них политики защиты от lp в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8feea-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="8feea-128">Кроме того, можно использовать Microsoft Cloud App Security для создания политик защиты от lp в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8feea-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="8feea-129">Однако рекомендуется использовать Microsoft 365 для создания политик DLP в облачных приложениях Майкрософт и управления ими.</span><span class="sxs-lookup"><span data-stu-id="8feea-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="8feea-130">Создание политики DLP в облачном приложении от корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8feea-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="8feea-131">Когда вы выбираете расположение для политики DLP, включаем расположение **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="8feea-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="8feea-132">Чтобы выбрать конкретное приложение или экземпляр, выберите **"Выбрать экземпляр".**</span><span class="sxs-lookup"><span data-stu-id="8feea-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="8feea-133">Если экземпляр не выбран, политика использует все подключенные приложения в клиенте Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8feea-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Расположения для применения политики](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US и Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="8feea-136">Вы можете выбрать различные действия для всех поддерживаемых облачных приложений, не в корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8feea-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="8feea-137">Для каждого приложения существуют различные возможные действия (зависит от API облачного приложения).</span><span class="sxs-lookup"><span data-stu-id="8feea-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Создание правила](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="8feea-139">При создании правила в политике DLP можно выбрать действие для облачных приложений, не в корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8feea-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="8feea-140">Чтобы ограничить сторонние приложения, выберите **"Ограничить сторонние приложения".**</span><span class="sxs-lookup"><span data-stu-id="8feea-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Ограничение сторонних приложений](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="8feea-142">Сведения о создании и настройке политик DLP см. в подстройки "Создание тестирования [и настройка политики DLP".](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="8feea-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="8feea-143">См. также</span><span class="sxs-lookup"><span data-stu-id="8feea-143">See Also</span></span>

- [<span data-ttu-id="8feea-144">Создание тестовой и настраиваемой политики DLP</span><span class="sxs-lookup"><span data-stu-id="8feea-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="8feea-145">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="8feea-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="8feea-146">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="8feea-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
