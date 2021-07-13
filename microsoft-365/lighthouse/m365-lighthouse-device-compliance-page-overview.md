---
title: Microsoft 365 Lighthouse Обзор страницы соответствия требованиям устройств
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
description: Для поставщиков управляемых служб (MSP) с Microsoft 365 Lighthouse, узнайте о странице соответствия требованиям устройства.
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395228"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="bd6e7-103">Microsoft 365 Lighthouse Обзор страницы соответствия требованиям устройств</span><span class="sxs-lookup"><span data-stu-id="bd6e7-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="bd6e7-104">Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют [требованиям.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="bd6e7-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="bd6e7-105">Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="bd6e7-106">Microsoft 365 Lighthouse позволяет просматривать сведения и сведения, связанные с соответствием требованиям устройств Intune для всех клиентов, выбрав **Устройства** в левой области навигации, чтобы открыть страницу соответствия требованиям устройства.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="bd6e7-107">На этой странице можно получить обзор состояния соответствия требованиям для клиентов, просмотреть список устройств для каждого клиента и получить отчеты о состоянии политик и параметров соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="bd6e7-108">Вкладка Обзор</span><span class="sxs-lookup"><span data-stu-id="bd6e7-108">Overview tab</span></span>  
  
<span data-ttu-id="bd6e7-109">На вкладке Обзор можно просмотреть состояние соответствия требованиям устройств для клиентов, просмотреть тенденции соответствия требованиям к устройствам и отслеживать, назначены ли им политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="bd6e7-110">Кроме того, можно просмотреть сведения о действиях и требованиях, предъявляемых к устройству клиента, на основе политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Снимок экрана вкладки Обзор.":::

## <a name="devices-tab"></a><span data-ttu-id="bd6e7-112">Вкладка Устройства</span><span class="sxs-lookup"><span data-stu-id="bd6e7-112">Devices tab</span></span>

<span data-ttu-id="bd6e7-113">На вкладке Устройства можно просмотреть список всех устройств-клиентов и отфильтровать список на основе следующих статусов соответствия требованиям: Compliant, Non-compliant, In Grace period и Not evaluated.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="bd6e7-114">Дополнительные сведения о различных состояниях соответствия см. в рубке [Monitor Intune Device compliance policies.](/mem/intune/protect/compliance-policy-monitor)</span><span class="sxs-lookup"><span data-stu-id="bd6e7-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="bd6e7-115">Выберите любое устройство, чтобы просмотреть дополнительные сведения о том, почему устройство находится в текущем состоянии соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="bd6e7-116">Если требуется принять меры на устройстве, можно просмотреть устройство в Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Снимок экрана вкладки Devices.":::

## <a name="policies-tab"></a><span data-ttu-id="bd6e7-118">Вкладка Политики</span><span class="sxs-lookup"><span data-stu-id="bd6e7-118">Policies tab</span></span>

<span data-ttu-id="bd6e7-119">На вкладке Политики можно просмотреть политики соответствия требованиям для клиентов и сравнить две или три политики одного типа платформы с помощью функции Compare на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="bd6e7-120">Вы также можете выбрать любую политику, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Снимок экрана вкладки Политики.":::

## <a name="settings-tab"></a><span data-ttu-id="bd6e7-122">Параметры вкладка</span><span class="sxs-lookup"><span data-stu-id="bd6e7-122">Settings tab</span></span>

<span data-ttu-id="bd6e7-123">Вкладка "Параметры" предоставляет сводный отчет о параметрах, не совместимых с соответствием требованиям на устройствах клиента.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="bd6e7-124">Выберите любую из строк отчета, чтобы просмотреть дополнительные сведения, в том числе сведения о том, к кому принадлежат не совместимые устройства.</span><span class="sxs-lookup"><span data-stu-id="bd6e7-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Снимок экрана Параметры вкладки.":::

## <a name="related-content"></a><span data-ttu-id="bd6e7-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd6e7-126">Related content</span></span>

<span data-ttu-id="bd6e7-127">[Microsoft 365 Lighthouse страницы пользователей](m365-lighthouse-users-page-overview.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="bd6e7-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="bd6e7-128">[Microsoft 365 Lighthouse (статья)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="bd6e7-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
