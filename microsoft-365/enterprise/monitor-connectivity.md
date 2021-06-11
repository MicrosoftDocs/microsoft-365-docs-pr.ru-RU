---
title: Проверка подключения Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: В этой статье вы узнаете о средствах и методах, которые можно использовать для мониторинга и Microsoft 365 подключения.
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538811"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="e0f36-103">Проверка подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0f36-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="e0f36-104">После развертывания Microsoft 365 вы можете Microsoft 365 подключение с помощью некоторых средств и методов ниже.</span><span class="sxs-lookup"><span data-stu-id="e0f36-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="e0f36-105">Вы хотите понять официальные [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) рекомендации по охране и непрерывности служб, а также рекомендации по использованию Microsoft 365 в [медленной сети.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="e0f36-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="e0f36-106">Вы также хотите захватить приложение [администрирования Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) и закладки нашего Microsoft 365 для [бизнеса - Справка администратора](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span><span class="sxs-lookup"><span data-stu-id="e0f36-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="e0f36-107">Мониторинг Microsoft 365 подключения</span><span class="sxs-lookup"><span data-stu-id="e0f36-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e0f36-108">**Получение уведомления о новых Microsoft 365 конечных точках**</span><span class="sxs-lookup"><span data-stu-id="e0f36-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="e0f36-109">Если вы управляете конечными точками [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)вы хотите получать уведомления при публикации новых конечных точек, вы можете подписаться на наш RSS-канал с помощью вашего любимого читателя RSS.</span><span class="sxs-lookup"><span data-stu-id="e0f36-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="e0f36-110">Вот как [подписаться через Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) или вы можете [иметь RSS-обновления каналов по электронной почте.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="e0f36-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="e0f36-111">**Используйте System Center для мониторинга Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e0f36-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="e0f36-112">Если вы используете Microsoft System Center, вы можете [](https://www.microsoft.com/download/details.aspx?id=43708) скачать пакет System Center управления для Office 365, чтобы начать мониторинг Microsoft 365 сегодня.</span><span class="sxs-lookup"><span data-stu-id="e0f36-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="e0f36-113">Дополнительные сведения см. в руководстве по операциям пакетов управления.</span><span class="sxs-lookup"><span data-stu-id="e0f36-113">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="e0f36-114">**Наблюдение за работоспособностью Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="e0f36-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="e0f36-115">Если вы подключаете Microsoft 365 Azure ExpressRoute для Microsoft 365, необходимо убедиться, что вы используете панель мониторинга состояния службы Microsoft 365, а также время устранения неполадок Azure с помощью [службы Azure Resource.](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="e0f36-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="e0f36-116">**Использование Azure AD Connect Health с AD FS**</span><span class="sxs-lookup"><span data-stu-id="e0f36-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="e0f36-117">Если вы используете службу AD FS для единой Sign-On с Microsoft 365, необходимо приступить к использованию Azure AD Подключение Health для мониторинга инфраструктуры [AD FS.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="e0f36-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="e0f36-118">**Программный мониторинг Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e0f36-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="e0f36-119">Обратитесь к нашим рекомендациям по [API Microsoft 365 управления.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="e0f36-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="e0f36-120">Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="e0f36-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e0f36-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e0f36-121">Related topics</span></span>

[<span data-ttu-id="e0f36-122">Настройка Microsoft 365 корпоративный служб и приложений</span><span class="sxs-lookup"><span data-stu-id="e0f36-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="e0f36-123">Подготовь организацию к Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e0f36-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="e0f36-124">Планирование сети и настройка производительности для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0f36-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="e0f36-125">Microsoft 365 интеграции с локальной средой</span><span class="sxs-lookup"><span data-stu-id="e0f36-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="e0f36-126">Управление Microsoft 365 конечными точками</span><span class="sxs-lookup"><span data-stu-id="e0f36-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
