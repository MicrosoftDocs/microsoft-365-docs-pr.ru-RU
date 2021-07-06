---
title: Использование политик предотвращения потери данных для облачных приложений, не в microsoft
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
ms.openlocfilehash: fbba87fc5bb3bbca7e67ba374e202098a22f4a5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300128"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="b6c6c-103">Используйте политики предотвращения потери данных для облачных приложений, не в microsoft (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="b6c6c-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="b6c6c-104">Политики предотвращения потери данных (DLP) для не microsoft cloud apps являются частью пакета функций Microsoft 365 DLP; С помощью этих функций можно обнаружить и защитить конфиденциальные элементы в Microsoft 365 службах.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="b6c6c-105">Дополнительные сведения обо всех предложениях Microsoft DLP см. в дополнительных сведениях [о предотвращении потери данных.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="b6c6c-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="b6c6c-106">Политики DLP можно использовать в облачных приложениях, не в microsoft, для мониторинга и обнаружения использования конфиденциальных элементов и их общего использования с помощью облачных приложений, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="b6c6c-107">Использование этих политик обеспечивает видимость и контроль, необходимые для обеспечения правильного использования и защиты этих политик, а также позволяет предотвратить рискованное поведение, которое может привести к их угрозе.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b6c6c-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="b6c6c-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="b6c6c-109">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="b6c6c-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="b6c6c-110">Прежде чем приступить к использованию политик DLP в облачных приложениях, [не в](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) microsoft, Microsoft 365 подписку и все надстройки.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="b6c6c-111">Чтобы получить доступ к этой функции и использовать ее, необходимо иметь одну из этих подписок или надстройок:</span><span class="sxs-lookup"><span data-stu-id="b6c6c-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="b6c6c-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b6c6c-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="b6c6c-113">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b6c6c-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="b6c6c-114">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b6c6c-114">Microsoft 365 E5 Security</span></span>

### <a name="permissions"></a><span data-ttu-id="b6c6c-115">Разрешения.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-115">Permissions</span></span>
<span data-ttu-id="b6c6c-116">Пользователь, создавший политику DLP, должен быть:</span><span class="sxs-lookup"><span data-stu-id="b6c6c-116">The user who creates the DLP policy should be a:</span></span>
- <span data-ttu-id="b6c6c-117">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="b6c6c-117">Global administrator</span></span>
- <span data-ttu-id="b6c6c-118">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="b6c6c-118">Compliance administrator</span></span>
- <span data-ttu-id="b6c6c-119">Администратор данных о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="b6c6c-119">Compliance data administrator</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="b6c6c-120">Подготовка среды Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b6c6c-120">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="b6c6c-121">Политики DLP для не microsoft cloud apps используют Cloud App Security DLP.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-121">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="b6c6c-122">Чтобы использовать его, необходимо подготовить Cloud App Security среду.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-122">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="b6c6c-123">Инструкции см. в [инструкции Set instant visibility, protection and governance actions for your apps.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="b6c6c-123">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="b6c6c-124">Подключение облачное приложение, не в microsoft</span><span class="sxs-lookup"><span data-stu-id="b6c6c-124">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="b6c6c-125">Чтобы использовать политику DLP в определенном облачном приложении, не связанном с Microsoft, приложение должно быть подключено к Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-125">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="b6c6c-126">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-126">For information, see:</span></span>

- [<span data-ttu-id="b6c6c-127">Подключение Box</span><span class="sxs-lookup"><span data-stu-id="b6c6c-127">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="b6c6c-128">Подключение Dropbox</span><span class="sxs-lookup"><span data-stu-id="b6c6c-128">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="b6c6c-129">Подключение G-Suite</span><span class="sxs-lookup"><span data-stu-id="b6c6c-129">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="b6c6c-130">Подключение Salesforce</span><span class="sxs-lookup"><span data-stu-id="b6c6c-130">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="b6c6c-131">Подключение Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="b6c6c-131">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="b6c6c-132">После подключения облачных приложений к Cloud App Security можно создать Microsoft 365 DLP-политики для них.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-132">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

> [!NOTE]
> <span data-ttu-id="b6c6c-133">Кроме того, можно использовать Microsoft Cloud App Security для создания политик DLP в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-133">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="b6c6c-134">Однако рекомендуется использовать Microsoft 365 для создания и управления политиками DLP в облачных приложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-134">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="b6c6c-135">Создание политики DLP в облачном приложении, не в microsoft</span><span class="sxs-lookup"><span data-stu-id="b6c6c-135">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="b6c6c-136">При выборе расположения для политики DLP включаем Microsoft Cloud App Security **расположение.**</span><span class="sxs-lookup"><span data-stu-id="b6c6c-136">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="b6c6c-137">Чтобы выбрать определенное приложение или экземпляр, выберите **выберите экземпляр .**</span><span class="sxs-lookup"><span data-stu-id="b6c6c-137">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="b6c6c-138">Если экземпляр не выбран, политика использует все подключенные приложения в Microsoft Cloud App Security клиенте.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-138">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Расположения для применения политики](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US и Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="b6c6c-141">Вы можете выбрать различные действия для каждого поддерживаемого облачного приложения, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-141">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="b6c6c-142">Для каждого приложения существуют различные возможные действия (зависит от API облачного приложения).</span><span class="sxs-lookup"><span data-stu-id="b6c6c-142">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Создание правила](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="b6c6c-144">При создании правила в политике DLP можно выбрать действие для не microsoft cloud apps.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-144">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="b6c6c-145">Чтобы ограничить сторонние приложения, выберите **Ограничение сторонних приложений.**</span><span class="sxs-lookup"><span data-stu-id="b6c6c-145">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Ограничение сторонних приложений](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> <span data-ttu-id="b6c6c-147">Политики DLP, применяемые к приложениям, не относя к Майкрософт, Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-147">DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="b6c6c-148">После создания политики DLP для приложения, не включаемого в Корпорацию Майкрософт, в Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-148">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="b6c6c-149">Сведения о создании и настройке политик DLP см. в таблице [Create test and tune a DLP policy.](./create-test-tune-dlp-policy.md)</span><span class="sxs-lookup"><span data-stu-id="b6c6c-149">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6c6c-150">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c6c-150">See Also</span></span>

- [<span data-ttu-id="b6c6c-151">Создание тестирования и настройка политики DLP</span><span class="sxs-lookup"><span data-stu-id="b6c6c-151">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md)
- [<span data-ttu-id="b6c6c-152">Начало работы со стандартной политикой защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="b6c6c-152">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="b6c6c-153">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="b6c6c-153">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md)
