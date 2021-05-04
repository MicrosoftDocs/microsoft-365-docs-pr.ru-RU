---
title: Используйте политики предотвращения потери данных для облачных приложений, не в microsoft (предварительный просмотр)
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
description: Узнайте, как использовать политики dlp для облачных приложений, не в microsoft.
ms.openlocfilehash: d4c5170cab01b1ca22701b13c7afbf4f2e0ba7da
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114137"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="201ca-103">Используйте политики предотвращения потери данных для облачных приложений, не в microsoft (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="201ca-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="201ca-104">Политики предотвращения потери данных (DLP) для не microsoft cloud apps являются частью пакета функций Microsoft 365 DLP; С помощью этих функций можно обнаружить и защитить конфиденциальные элементы в Microsoft 365 службах.</span><span class="sxs-lookup"><span data-stu-id="201ca-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="201ca-105">Дополнительные сведения обо всех предложениях Microsoft DLP см. в дополнительных сведениях [о предотвращении потери данных.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="201ca-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="201ca-106">Политики DLP можно использовать в облачных приложениях, не в microsoft, для мониторинга и обнаружения использования конфиденциальных элементов и их общего использования с помощью облачных приложений, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="201ca-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="201ca-107">Использование этих политик обеспечивает видимость и контроль, необходимые для обеспечения правильного использования и защиты этих политик, а также позволяет предотвратить рискованное поведение, которое может привести к их угрозе.</span><span class="sxs-lookup"><span data-stu-id="201ca-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="201ca-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="201ca-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="201ca-109">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="201ca-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="201ca-110">Прежде чем приступить к использованию политик DLP в облачных приложениях, [не в](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) microsoft, Microsoft 365 подписку и все надстройки.</span><span class="sxs-lookup"><span data-stu-id="201ca-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="201ca-111">Чтобы получить доступ к этой функции и использовать ее, необходимо иметь одну из этих подписок или надстройок:</span><span class="sxs-lookup"><span data-stu-id="201ca-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="201ca-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="201ca-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="201ca-113">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="201ca-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="201ca-114">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="201ca-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="201ca-115">Подготовка среды Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="201ca-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="201ca-116">Политики DLP для не microsoft cloud apps используют Cloud App Security DLP.</span><span class="sxs-lookup"><span data-stu-id="201ca-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="201ca-117">Чтобы использовать его, необходимо подготовить Cloud App Security среду.</span><span class="sxs-lookup"><span data-stu-id="201ca-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="201ca-118">Инструкции см. в [инструкции Set instant visibility, protection and governance actions for your apps.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="201ca-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="201ca-119">Подключение облачное приложение, не в microsoft</span><span class="sxs-lookup"><span data-stu-id="201ca-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="201ca-120">Чтобы использовать политику DLP в определенном облачном приложении, не связанном с Microsoft, приложение должно быть подключено к Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="201ca-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="201ca-121">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="201ca-121">For information, see:</span></span>

- [<span data-ttu-id="201ca-122">Подключение Box</span><span class="sxs-lookup"><span data-stu-id="201ca-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="201ca-123">Подключение Dropbox</span><span class="sxs-lookup"><span data-stu-id="201ca-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="201ca-124">Подключение G-Suite</span><span class="sxs-lookup"><span data-stu-id="201ca-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="201ca-125">Подключение Salesforce</span><span class="sxs-lookup"><span data-stu-id="201ca-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="201ca-126">Подключение Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="201ca-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="201ca-127">После подключения облачных приложений к Cloud App Security можно создать Microsoft 365 DLP-политики для них.</span><span class="sxs-lookup"><span data-stu-id="201ca-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="201ca-128">Кроме того, можно использовать Microsoft Cloud App Security для создания политик DLP в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="201ca-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="201ca-129">Однако рекомендуется использовать Microsoft 365 для создания и управления политиками DLP в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="201ca-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="201ca-130">Создание политики DLP в облачном приложении, не в microsoft</span><span class="sxs-lookup"><span data-stu-id="201ca-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="201ca-131">При выборе расположения для политики DLP включаем Microsoft Cloud App Security **расположение.**</span><span class="sxs-lookup"><span data-stu-id="201ca-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="201ca-132">Чтобы выбрать определенное приложение или экземпляр, выберите **выберите экземпляр .**</span><span class="sxs-lookup"><span data-stu-id="201ca-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="201ca-133">Если экземпляр не выбран, политика использует все подключенные приложения в Microsoft Cloud App Security клиенте.</span><span class="sxs-lookup"><span data-stu-id="201ca-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Расположения для применения политики](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US и Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="201ca-136">Вы можете выбрать различные действия для каждого поддерживаемого облачного приложения, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="201ca-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="201ca-137">Для каждого приложения существуют различные возможные действия (зависит от API облачного приложения).</span><span class="sxs-lookup"><span data-stu-id="201ca-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Создание правила](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="201ca-139">При создании правила в политике DLP можно выбрать действие для не microsoft cloud apps.</span><span class="sxs-lookup"><span data-stu-id="201ca-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="201ca-140">Чтобы ограничить сторонние приложения, выберите **Ограничение сторонних приложений.**</span><span class="sxs-lookup"><span data-stu-id="201ca-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Ограничение сторонних приложений](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="201ca-142">Сведения о создании и настройке политик DLP см. в таблице [Create test and tune a DLP policy.](./create-test-tune-dlp-policy.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="201ca-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="201ca-143">См. также</span><span class="sxs-lookup"><span data-stu-id="201ca-143">See Also</span></span>

- [<span data-ttu-id="201ca-144">Создание тестирования и настройка политики DLP</span><span class="sxs-lookup"><span data-stu-id="201ca-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="201ca-145">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="201ca-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="201ca-146">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="201ca-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)