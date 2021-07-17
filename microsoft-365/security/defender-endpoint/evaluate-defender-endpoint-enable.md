---
title: Пилотный защитник для оценки конечной точки
description: Внося Microsoft 365 Defender пробную или пилотную среду.
keywords: Microsoft 365 Defender пробной версии попробуйте Microsoft 365 Defender, оцените Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки, пилот Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователей, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458640"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="bbc53-104">Пилотная оценка MDE</span><span class="sxs-lookup"><span data-stu-id="bbc53-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="bbc53-105">Для того, чтобы направлять вас через типичное развертывание, этот сценарий будет охватывать только использование Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bbc53-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="bbc53-106">Defender for Endpoint поддерживает использование других средств бортового использования, но не покрывает эти сценарии в руководстве по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bbc53-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="bbc53-107">Дополнительные сведения см. в таблице [Onboard devices to Microsoft Defender for Endpoint.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bbc53-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="bbc53-108">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="bbc53-108">Step 1.</span></span> <span data-ttu-id="bbc53-109">Проверка состояния лицензии</span><span class="sxs-lookup"><span data-stu-id="bbc53-109">Check license state</span></span>

<span data-ttu-id="bbc53-110">Проверка состояния лицензии и правильного ее состояния можно сделать через центр администрирования или на **портале Microsoft Azure.**</span><span class="sxs-lookup"><span data-stu-id="bbc53-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="bbc53-111">Чтобы просмотреть лицензии, перейдите на портал **Microsoft Azure и** перейдите в раздел лицензии Microsoft Azure [портала](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span><span class="sxs-lookup"><span data-stu-id="bbc53-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Изображение страницы лицензирования Azure](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="bbc53-113">Поочередно в центре администрирования перейдите к **подпискам на**  >  **биллинг.**</span><span class="sxs-lookup"><span data-stu-id="bbc53-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="bbc53-114">На экране вы увидите все предварительные лицензии и их текущее **состояние.**</span><span class="sxs-lookup"><span data-stu-id="bbc53-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Изображение лицензий на выставление счета](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="bbc53-116">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="bbc53-116">Step 2.</span></span> <span data-ttu-id="bbc53-117">Конечные точки на борту с использованием любого из поддерживаемых средств управления</span><span class="sxs-lookup"><span data-stu-id="bbc53-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="bbc53-118">В [разделе Развертывание](deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bbc53-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="bbc53-119">Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.</span><span class="sxs-lookup"><span data-stu-id="bbc53-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="bbc53-120">После определения архитектуры необходимо решить, какой метод развертывания использовать.</span><span class="sxs-lookup"><span data-stu-id="bbc53-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="bbc53-121">Инструмент развертывания, который вы выбираете, влияет на то, как вы работаете с конечными точками на борту службы.</span><span class="sxs-lookup"><span data-stu-id="bbc53-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="bbc53-122">Параметры onboarding tool</span><span class="sxs-lookup"><span data-stu-id="bbc53-122">Onboarding tool options</span></span>

<span data-ttu-id="bbc53-123">В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.</span><span class="sxs-lookup"><span data-stu-id="bbc53-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="bbc53-124">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="bbc53-124">Endpoint</span></span>     | <span data-ttu-id="bbc53-125">Параметры инструмента</span><span class="sxs-lookup"><span data-stu-id="bbc53-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="bbc53-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="bbc53-126">**Windows**</span></span>  |  [<span data-ttu-id="bbc53-127">Локальный скрипт (до 10 устройств)</span><span class="sxs-lookup"><span data-stu-id="bbc53-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="bbc53-128">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="bbc53-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="bbc53-129">Microsoft Endpoint Manager/ Диспетчер мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="bbc53-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="bbc53-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bbc53-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="bbc53-131">Скрипты VDI</span><span class="sxs-lookup"><span data-stu-id="bbc53-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="bbc53-132">Интеграция с Защитником Azure</span><span class="sxs-lookup"><span data-stu-id="bbc53-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="bbc53-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="bbc53-133">**macOS**</span></span>    | [<span data-ttu-id="bbc53-134">Местные сценарии</span><span class="sxs-lookup"><span data-stu-id="bbc53-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="bbc53-135">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="bbc53-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="bbc53-136">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="bbc53-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="bbc53-137">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="bbc53-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="bbc53-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="bbc53-138">**Linux Server**</span></span> | [<span data-ttu-id="bbc53-139">Локальный скрипт</span><span class="sxs-lookup"><span data-stu-id="bbc53-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="bbc53-140">Puppet</span><span class="sxs-lookup"><span data-stu-id="bbc53-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="bbc53-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="bbc53-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="bbc53-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="bbc53-142">**iOS**</span></span>      | [<span data-ttu-id="bbc53-143">На основе приложения</span><span class="sxs-lookup"><span data-stu-id="bbc53-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="bbc53-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="bbc53-144">**Android**</span></span>  | [<span data-ttu-id="bbc53-145">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="bbc53-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
