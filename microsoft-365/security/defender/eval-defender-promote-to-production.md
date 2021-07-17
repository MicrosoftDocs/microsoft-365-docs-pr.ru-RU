---
title: Продвижение среды Microsoft 365 Defender в производственную, Microsoft 365 Defender оценку, попробуйте оценку, сохраняйте оценку, производственную оценку
description: Используйте эту статью для продвижения эквивалентов MDI, MDO, MDE и MCAS в живую среду в Microsoft 365 Defender или M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458747"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="2b314-103">Продвижение среды Microsoft 365 Defender в производство</span><span class="sxs-lookup"><span data-stu-id="2b314-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="2b314-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2b314-104">**Applies to:**</span></span>
- <span data-ttu-id="2b314-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b314-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="2b314-106">Чтобы повысить Microsoft 365 Defender среды оценки до производства, сначала приобретите необходимую лицензию.</span><span class="sxs-lookup"><span data-stu-id="2b314-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="2b314-107">Следуйте шагам в Создании среды [eval](eval-create-eval-environment.md) и приобретайте лицензию Office 365 E5 (вместо выбора бесплатной пробной пробной части Start).</span><span class="sxs-lookup"><span data-stu-id="2b314-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="2b314-108">Затем выполните любую дополнительную конфигурацию и расширите пилотные группы, пока они не достигнут полного производства.</span><span class="sxs-lookup"><span data-stu-id="2b314-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="2b314-109">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="2b314-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="2b314-110">Defender for Identity не требует дополнительной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b314-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="2b314-111">Просто убедитесь, что вы приобрели необходимые лицензии и установили датчик на всех контроллерах домена Active Directory и серверах федерации Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="2b314-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="2b314-112">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="2b314-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="2b314-113">После успешной оценки или пилотирования MDO он может быть повышен до всей производственной среды.</span><span class="sxs-lookup"><span data-stu-id="2b314-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="2b314-114">Приобретение и предоставление необходимых лицензий и назначение их пользователям производства.</span><span class="sxs-lookup"><span data-stu-id="2b314-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="2b314-115">Повторно запустите рекомендуемые базовые конфигурации политики (стандартные или строгие) для производственного домена электронной почты или определенных групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="2b314-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="2b314-116">Необязательно создавать и настраивать настраиваемые политики MDO в отношении производственного домена электронной почты или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="2b314-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="2b314-117">Однако помните, что все назначенные базовые политики всегда будут иметь приоритет над настраиваемой политикой.</span><span class="sxs-lookup"><span data-stu-id="2b314-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="2b314-118">Обновите публичную запись MX для вашего домена электронной почты для решения непосредственно в EOP.</span><span class="sxs-lookup"><span data-stu-id="2b314-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="2b314-119">Отключите все сторонние шлюзы SMTP и отключите или удалите все соединители EXO, связанные с этим ретранслятором.</span><span class="sxs-lookup"><span data-stu-id="2b314-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="2b314-120">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2b314-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="2b314-121">Чтобы повысить среду оценки Microsoft Defender для конечных точек с пилотного до производственного, просто на борту дополнительных конечных точек службы с помощью любых поддерживаемых средств [и методов.](/defender-endpoint/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="2b314-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="2b314-122">Используйте следующие общие рекомендации, чтобы использовать дополнительные устройства в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2b314-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="2b314-123">Убедитесь, что устройство выполняет [минимальные требования.](/defender-endpoint/minimum-requirements)</span><span class="sxs-lookup"><span data-stu-id="2b314-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="2b314-124">В зависимости от устройства следуйте шагам конфигурации, предусмотренным в разделе onboarding портала Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b314-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="2b314-125">Используйте соответствующий инструмент управления и метод развертывания для устройств.</span><span class="sxs-lookup"><span data-stu-id="2b314-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="2b314-126">Запустите тест обнаружения, чтобы убедиться, что устройства правильно на борту и отчеты службе.</span><span class="sxs-lookup"><span data-stu-id="2b314-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="2b314-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2b314-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="2b314-128">Microsoft Cloud App Security не требует дополнительной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b314-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="2b314-129">Просто убедитесь, что вы приобрели необходимые лицензии.</span><span class="sxs-lookup"><span data-stu-id="2b314-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="2b314-130">Если развертывание было развернуто в определенных группах пользователей, необходимо увеличить область действия этих групп до достижения производственного масштаба.</span><span class="sxs-lookup"><span data-stu-id="2b314-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

