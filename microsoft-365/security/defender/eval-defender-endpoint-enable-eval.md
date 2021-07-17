---
title: Включить microsoft Defender для оценки конечной точки, активировать оценку для MDE
description: Включите Microsoft 365 Defender пробную или пилотную среду, включая проверку состояния лицензии и onboarding enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458581"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="433d8-103">Включить среду оценки конечных точек Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="433d8-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="433d8-104">В этой статье вы сможете с помощью производственных устройств принять меры по настройке среды оценки для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="433d8-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="433d8-105">Microsoft Defender для endpoint также поставляется с лабораторией оценки в продукте, где можно добавить предварительно настроенные устройства и запустить моделирование для оценки возможностей платформы.</span><span class="sxs-lookup"><span data-stu-id="433d8-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="433d8-106">В лаборатории имеется упрощенная настройка, которая поможет быстро продемонстрировать значение Microsoft Defender для enpdoint, включая рекомендации по многим функциям, таким как расширенный анализ охоты и аналитика угроз.</span><span class="sxs-lookup"><span data-stu-id="433d8-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="433d8-107">Дополнительные сведения см. в [дополнительных сведениях о возможностях Оценки.](/defender-endpoint/evaluation-lab.md)</span><span class="sxs-lookup"><span data-stu-id="433d8-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="433d8-108">Основное отличие руководства, представленного в этой статье, от лаборатории оценки состоит в том, что среда оценки использует производственные устройства, в то время как лаборатория оценки использует непроизводимые устройства.</span><span class="sxs-lookup"><span data-stu-id="433d8-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="433d8-109">Чтобы включить оценку для Microsoft Defender для конечной точки, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="433d8-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Действия, направленные на то, чтобы включить Microsoft Defender для конечной точки в среде оценки Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="433d8-111">Шаг 1. Проверка состояния лицензии</span><span class="sxs-lookup"><span data-stu-id="433d8-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="433d8-112">Шаг 2. Конечные точки на борту</span><span class="sxs-lookup"><span data-stu-id="433d8-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="433d8-113">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="433d8-113">Step 1.</span></span> <span data-ttu-id="433d8-114">Проверка состояния лицензии</span><span class="sxs-lookup"><span data-stu-id="433d8-114">Check license state</span></span>

<span data-ttu-id="433d8-115">Сначала необходимо проверить состояние лицензии, чтобы убедиться, что оно было правильно заложено.</span><span class="sxs-lookup"><span data-stu-id="433d8-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="433d8-116">Это можно сделать через центр администрирования или через **портал Microsoft Azure.**</span><span class="sxs-lookup"><span data-stu-id="433d8-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="433d8-117">Чтобы просмотреть лицензии, перейдите на портал **Microsoft Azure и** перейдите в раздел лицензии Microsoft Azure [портала](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span><span class="sxs-lookup"><span data-stu-id="433d8-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Изображение страницы лицензирования Azure](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="433d8-119">Поочередно в центре администрирования перейдите к **подпискам на**  >  **биллинг.**</span><span class="sxs-lookup"><span data-stu-id="433d8-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="433d8-120">На экране вы увидите все предварительные лицензии и их текущее **состояние.**</span><span class="sxs-lookup"><span data-stu-id="433d8-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Изображение лицензий на выставление счета](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="433d8-122">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="433d8-122">Step 2.</span></span> <span data-ttu-id="433d8-123">Конечные точки на борту с использованием любого из поддерживаемых средств управления</span><span class="sxs-lookup"><span data-stu-id="433d8-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="433d8-124">После проверки правильного состояния лицензии можно запустить бортовые устройства в службу.</span><span class="sxs-lookup"><span data-stu-id="433d8-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="433d8-125">Для оценки Microsoft Defender для конечной точки рекомендуется выбрать несколько Windows 10 для проведения оценки.</span><span class="sxs-lookup"><span data-stu-id="433d8-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="433d8-126">В [разделе Развертывание](../defender-endpoint/deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="433d8-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="433d8-127">Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.</span><span class="sxs-lookup"><span data-stu-id="433d8-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="433d8-128">Параметры onboarding tool</span><span class="sxs-lookup"><span data-stu-id="433d8-128">Onboarding tool options</span></span>

<span data-ttu-id="433d8-129">В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.</span><span class="sxs-lookup"><span data-stu-id="433d8-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="433d8-130">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="433d8-130">Endpoint</span></span> | <span data-ttu-id="433d8-131">Параметры инструмента</span><span class="sxs-lookup"><span data-stu-id="433d8-131">Tool options</span></span>
:---|:---
<span data-ttu-id="433d8-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="433d8-132">**Windows**</span></span> | <span data-ttu-id="433d8-133">[Локальный скрипт (до 10 устройств),](../defender-endpoint/configure-endpoints-script.md)групповой политики [,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/](../defender-endpoint/configure-endpoints-mdm.md)Диспетчер мобильных устройств , [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [сценарии VDI](../defender-endpoint/configure-endpoints-vdi.md), [интеграция](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) с Azure Defender</span><span class="sxs-lookup"><span data-stu-id="433d8-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="433d8-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="433d8-134">**macOS**</span></span> | <span data-ttu-id="433d8-135">[Локальные сценарии](../defender-endpoint/mac-install-manually.md) [, Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), управление [мобильными устройствами](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="433d8-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="433d8-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="433d8-136">**Linux Server**</span></span> | <span data-ttu-id="433d8-137">[Локальный](../defender-endpoint/linux-install-manually.md)  [сценарий](../defender-endpoint/linux-install-with-puppet.md), Кукольный ,  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="433d8-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="433d8-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="433d8-138">**iOS**</span></span> | [<span data-ttu-id="433d8-139">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="433d8-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="433d8-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="433d8-140">**Android**</span></span> | [<span data-ttu-id="433d8-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="433d8-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="433d8-142">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="433d8-142">Next step</span></span>
[<span data-ttu-id="433d8-143">Настройка пилотного проекта для Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="433d8-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="433d8-144">Возвращение к обзору [оценки Microsoft Defender для конечной точки](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="433d8-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="433d8-145">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="433d8-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>