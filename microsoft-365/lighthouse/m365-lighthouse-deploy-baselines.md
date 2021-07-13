---
title: Развертывание Microsoft 365 Lighthouse базовых показателей
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Для поставщиков управляемых служб (MSP) с помощью Microsoft 365 Lighthouse узнайте, как развернуть Microsoft 365 Lighthouse базовых данных.
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395365"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="086dd-103">Развертывание Microsoft 365 Lighthouse базовых показателей</span><span class="sxs-lookup"><span data-stu-id="086dd-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="086dd-104">Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют [требованиям.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="086dd-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="086dd-105">Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="086dd-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="086dd-106">Microsoft 365 Lighthouse позволяет развертывать стандартные управляемые конфигурации клиента для защиты пользователей, устройств и данных клиента.</span><span class="sxs-lookup"><span data-stu-id="086dd-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="086dd-107">Существует шесть базовых конфигураций по умолчанию, которые являются стандартными с Microsoft 365 Lighthouse:</span><span class="sxs-lookup"><span data-stu-id="086dd-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="086dd-108">Требовать MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="086dd-108">Require MFA for admins</span></span>
- <span data-ttu-id="086dd-109">Требовать MFA для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="086dd-109">Require MFA for end users</span></span>
- <span data-ttu-id="086dd-110">Блокировка проверки подлинности в устаревших версиях</span><span class="sxs-lookup"><span data-stu-id="086dd-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="086dd-111">Настройка регистрации устройств в Microsoft Endpoint Manager - Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="086dd-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="086dd-112">Настройка антивирусной политики Defender для Windows устройств</span><span class="sxs-lookup"><span data-stu-id="086dd-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="086dd-113">Настройка политики соответствия требованиям для Windows устройств</span><span class="sxs-lookup"><span data-stu-id="086dd-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="086dd-114">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="086dd-114">Before you begin</span></span>

<span data-ttu-id="086dd-115">Убедитесь, что вы и клиенты соответствуют требованиям, указанным в требованиях [к Microsoft 365 Lighthouse.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="086dd-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="086dd-116">Дополнительные данные о базовой линии по умолчанию</span><span class="sxs-lookup"><span data-stu-id="086dd-116">Learn more about the default baseline</span></span>

<span data-ttu-id="086dd-117">Выберите **Базовые параметры** из левой области навигации, чтобы открыть страницу Базовые.</span><span class="sxs-lookup"><span data-stu-id="086dd-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="086dd-118">Вы увидите, что базовый уровень по умолчанию уже добавлен в группу клиентов по умолчанию (все клиенты).</span><span class="sxs-lookup"><span data-stu-id="086dd-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="086dd-119">Чтобы просмотреть базовые конфигурации по умолчанию, выберите **базовый просмотр,** чтобы открыть базовую страницу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="086dd-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="086dd-120">Конфигурации перечислены в качестве этапов развертывания.</span><span class="sxs-lookup"><span data-stu-id="086dd-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="086dd-121">Выберите любой из этапов развертывания, чтобы просмотреть сведения о развертывании и влияние пользователя.</span><span class="sxs-lookup"><span data-stu-id="086dd-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Снимок экрана базовой страницы по умолчанию.>.":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="086dd-123">Развертывание базовой конфигурации</span><span class="sxs-lookup"><span data-stu-id="086dd-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="086dd-124">На левой странице навигации выберите **"Клиенты",** чтобы просмотреть список ваших бортовых клиентов.</span><span class="sxs-lookup"><span data-stu-id="086dd-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="086dd-125">Выберите клиента, в который необходимо развернуть базовую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="086dd-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="086dd-126">Выберите **вкладку План** развертывания, чтобы увидеть все этапы развертывания из базовой базы, добавленной в план развертывания клиента.</span><span class="sxs-lookup"><span data-stu-id="086dd-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="086dd-127">Выберите шаг развертывания, чтобы открыть страницу шаг развертывания.</span><span class="sxs-lookup"><span data-stu-id="086dd-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="086dd-128">Выберите **Применить,** чтобы применить выбранный шаг развертывания к клиенту.</span><span class="sxs-lookup"><span data-stu-id="086dd-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="086dd-129">Если на шаге развертывания указано: "Это действие требует ручного шага", выполните ручной шаг, чтобы шаг развертывания был применен правильно.</span><span class="sxs-lookup"><span data-stu-id="086dd-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="086dd-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="086dd-130">Related content</span></span>

<span data-ttu-id="086dd-131">[Обзор использования базовых данных для развертывания стандартных конфигураций клиента](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="086dd-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="086dd-132">[Microsoft 365 Lighthouse (статья)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="086dd-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>