---
title: Использование политик защиты от потери данных для облачных приложений не от Майкрософт (Предварительная версия)
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
description: Узнайте, как использовать политики защиты от потери данных для облачных приложений не Майкрософт.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649660"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="05cc0-103">Использование политик защиты от потери данных для облачных приложений не от Майкрософт (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="05cc0-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="05cc0-104">Политики защиты от потери данных (DLP) для облачных приложений, отличных от Майкрософт, входят в состав набора функций Microsoft 365 DLP; с помощью этих функций можно обнаруживать конфиденциальные элементы в службах Microsoft 365 и защищать их.</span><span class="sxs-lookup"><span data-stu-id="05cc0-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="05cc0-105">Для получения дополнительных сведений о всех возможностях системы защиты от потери данных (Майкрософт) обратитесь к разделу [Обзор защиты от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="05cc0-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="05cc0-106">Политики защиты от потери данных можно использовать в облачных приложениях сторонних производителей для отслеживания и обнаружения использования конфиденциальных элементов и совместного использования облачных приложений не от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05cc0-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="05cc0-107">Использование этих политик обеспечивает видимость и контроль, необходимые для того, чтобы убедиться, что они правильно используются и защищены, и помогает предотвратить опасные функции, которые могут нарушить их безопасность.</span><span class="sxs-lookup"><span data-stu-id="05cc0-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="05cc0-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="05cc0-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="05cc0-109">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="05cc0-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="05cc0-110">Прежде чем приступать к использованию политик защиты от потери данных в облачных приложениях, отличных от Майкрософт, подтвердите вашу [подписку на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и все надстройки.</span><span class="sxs-lookup"><span data-stu-id="05cc0-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="05cc0-111">Чтобы получить доступ к этой функции и использовать ее, необходима одна из следующих подписок или надстроек:</span><span class="sxs-lookup"><span data-stu-id="05cc0-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="05cc0-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="05cc0-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="05cc0-113">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="05cc0-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="05cc0-114">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="05cc0-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="05cc0-115">Подготовка среды Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="05cc0-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="05cc0-116">Политики защиты от потери данных в облачных приложениях, отличных от Майкрософт, используют возможности Cloud App Security DLP.</span><span class="sxs-lookup"><span data-stu-id="05cc0-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="05cc0-117">Чтобы использовать ее, необходимо подготовить среду Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="05cc0-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="05cc0-118">Инструкции: [Set Мгновенная видимость, защита и действия по управлению для ваших приложений](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span><span class="sxs-lookup"><span data-stu-id="05cc0-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="05cc0-119">Подключение облачного приложения, не относящегося к корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="05cc0-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="05cc0-120">Чтобы использовать политику защиты от потери данных для конкретного облачного приложения, отличного от Майкрософт, приложение должно быть подключено к Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="05cc0-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="05cc0-121">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="05cc0-121">For information, see:</span></span>

- [<span data-ttu-id="05cc0-122">Поле подключения</span><span class="sxs-lookup"><span data-stu-id="05cc0-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="05cc0-123">Подключение к Dropbox</span><span class="sxs-lookup"><span data-stu-id="05cc0-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="05cc0-124">Подключение G – Suite</span><span class="sxs-lookup"><span data-stu-id="05cc0-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="05cc0-125">Подключение Salesforce</span><span class="sxs-lookup"><span data-stu-id="05cc0-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="05cc0-126">Подключение Cisco Вебекс</span><span class="sxs-lookup"><span data-stu-id="05cc0-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="05cc0-127">После подключения облачных приложений к Cloud App Security вы можете создать для них политики защиты от потери данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05cc0-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="05cc0-128">Кроме того, можно использовать Microsoft Cloud App Security для создания политик защиты от потери данных в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05cc0-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="05cc0-129">Тем не менее, рекомендуется использовать Microsoft 365 для создания политик защиты от потери данных и управления ими в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05cc0-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="05cc0-130">Создание политики защиты от потери данных для облачного приложения, отличного от Майкрософт</span><span class="sxs-lookup"><span data-stu-id="05cc0-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="05cc0-131">При выборе расположения для политики защиты от потери данных включите расположение **Microsoft Cloud App Security** .</span><span class="sxs-lookup"><span data-stu-id="05cc0-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="05cc0-132">Чтобы выбрать конкретное приложение или экземпляр, выберите **выбрать экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="05cc0-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="05cc0-133">Если вы не выбираете экземпляр, политика использует все подключенные приложения в вашем клиенте Cloud App Security (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="05cc0-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Расположения для применения политики](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box — США и Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="05cc0-136">Вы можете выбрать различные действия для каждого поддерживаемого облачного приложения, не относящегося к корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05cc0-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="05cc0-137">Для каждого приложения возможны различные действия (зависит от приложения Cloud App API).</span><span class="sxs-lookup"><span data-stu-id="05cc0-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Создание правила](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="05cc0-139">Когда вы создаете правило в политике защиты от потери данных, вы можете выбрать действие для облачных приложений, не относящихся к корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="05cc0-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="05cc0-140">Чтобы ограничить сторонние приложения, выберите пункт **ограничить приложения сторонних производителей**.</span><span class="sxs-lookup"><span data-stu-id="05cc0-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Ограничение приложений сторонних производителей](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="05cc0-142">Сведения о создании и настройке политик защиты от потери данных можно найти [в статье Create Test и Настройка политики DLP](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="05cc0-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="05cc0-143">См. также</span><span class="sxs-lookup"><span data-stu-id="05cc0-143">See Also</span></span>

- [<span data-ttu-id="05cc0-144">Создание теста и Настройка политики DLP</span><span class="sxs-lookup"><span data-stu-id="05cc0-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="05cc0-145">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="05cc0-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="05cc0-146">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="05cc0-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
