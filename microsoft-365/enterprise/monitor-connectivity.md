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
description: В этой статье вы узнаете о средствах и методах, которые можно использовать для отслеживания и поддержки подключения к Microsoft 365.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692974"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="02eb7-103">Проверка подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02eb7-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="02eb7-104">После развертывания Microsoft 365 вы можете поддерживать подключение к Microsoft 365 с помощью некоторых средств и методов, которые приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="02eb7-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="02eb7-105">Вам необходимо понять официальные [](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) рекомендации по обеспечению безопасности и непрерывности обслуживания, а также нашим рекомендациям по использованию [Microsoft 365 в медленных сетях.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="02eb7-105">You'll want to understand the official [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="02eb7-106">Вы также захотите захватить приложение для администрирования [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) и закладки microsoft 365 для бизнеса [справку для администраторов.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="02eb7-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="02eb7-107">Мониторинг подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02eb7-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="02eb7-108">**Получение уведомлений о новых конечных точках Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="02eb7-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="02eb7-109">Если вы управляете конечными точками [Microsoft 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)вы хотите получать уведомления при публикации новых конечных точек, вы можете подписаться на наш RSS-канал с помощью вашего любимого RSS-читателя.</span><span class="sxs-lookup"><span data-stu-id="02eb7-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="02eb7-110">Вот как [подписаться через Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) или вы можете отправить вам по электронной почте обновления [RSS-канала.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="02eb7-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="02eb7-111">**Использование System Center для мониторинга Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="02eb7-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="02eb7-112">Если вы используете Microsoft System Center, вы можете скачать [пакет управления System Center для Office 365,](https://www.microsoft.com/download/details.aspx?id=43708) чтобы начать мониторинг Microsoft 365 уже сегодня.</span><span class="sxs-lookup"><span data-stu-id="02eb7-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="02eb7-113">Дополнительные сведения см. в руководстве по работе с пакетом управления или в записи блога "Мониторинг [Office 365 с помощью System Centre Operations Manager"](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="02eb7-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="02eb7-114">**Наблюдение за работоспособностью Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="02eb7-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="02eb7-115">При подключении к Microsoft 365 с помощью Azure ExpressRoute для Microsoft 365 необходимо убедиться, что вы используете панель мониторинга состояния службы Microsoft 365, а также Azure, сокращая время устранения неполадок с состоянием [ресурсов Azure](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="02eb7-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="02eb7-116">**Использование Azure AD Connect Health с AD FS**</span><span class="sxs-lookup"><span data-stu-id="02eb7-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="02eb7-117">Если вы используете AD FS для единого Sign-On с Microsoft 365, вам необходимо начать использовать Azure AD Connect Health для отслеживания инфраструктуры [AD FS.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/)</span><span class="sxs-lookup"><span data-stu-id="02eb7-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span></span>  <br/> |
|<span data-ttu-id="02eb7-118">**Программный мониторинг Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="02eb7-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="02eb7-119">Обратитесь к нашим рекомендациям по API управления [Microsoft 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="02eb7-119">Refer to our guidance on the [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="02eb7-120">Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span><span class="sxs-lookup"><span data-stu-id="02eb7-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="02eb7-121">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="02eb7-121">Related topics</span></span>

[<span data-ttu-id="02eb7-122">Настройка служб и приложений Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="02eb7-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="02eb7-123">Подготовьтесь к microsoft 365 корпоративный для своей организации</span><span class="sxs-lookup"><span data-stu-id="02eb7-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="02eb7-124">Планирование сети и настройка производительности для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02eb7-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="02eb7-125">Интеграция Microsoft 365 с локальной средой</span><span class="sxs-lookup"><span data-stu-id="02eb7-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="02eb7-126">Управление конечными точками Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02eb7-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
