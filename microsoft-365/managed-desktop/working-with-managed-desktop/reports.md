---
title: Работа с отчетами
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917686"
---
# <a name="work-with-reports"></a><span data-ttu-id="c3ca5-103">Работа с отчетами</span><span class="sxs-lookup"><span data-stu-id="c3ca5-103">Work with reports</span></span>

<span data-ttu-id="c3ca5-104">Microsoft Managed Desktop предоставляет несколько отчетов и панелей мониторинга, которые ИТ-администраторы в организации могут использовать для понимания различных аспектов популяции устройств.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-104">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="c3ca5-105">Отчеты можно найти в двух местах: [в Microsoft Endpoint Manager](https://endpoint.microsoft.com) и в Центре администрирования Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)</span><span class="sxs-lookup"><span data-stu-id="c3ca5-105"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="c3ca5-106">Отчеты в Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c3ca5-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="c3ca5-107">Консоль Microsoft Endpoint Manager объединяет отчеты из нескольких продуктов в одном расположении, чтобы помочь вам отслеживать и исследовать проблемы с конфигурацией и устройствами организации Azure AD ("клиент").</span><span class="sxs-lookup"><span data-stu-id="c3ca5-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="c3ca5-108">Рабочий стол Microsoft Managed имеет раздел **"Отчеты"** в основном меню, в котором можно найти отчеты, специфические для управления устройствами, зарегистрированными в Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="c3ca5-109">Эти отчеты включают:</span><span class="sxs-lookup"><span data-stu-id="c3ca5-109">These reports include:</span></span>
- <span data-ttu-id="c3ca5-110">**Управляемые устройства**  >  **Обновления функций.** В этом представлении показан общий статус обновлений функций на управляемых настольных устройствах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="c3ca5-111">**Управляемые устройства**  >  **Обновления Office.** В этом представлении показан общий статус обновлений Office на управляемых настольных устройствах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="c3ca5-112">Кроме того, в нескольких местах в Microsoft Endpoint Manager можно фильтровать отчеты из других групп продуктов, чтобы конкретно включать или исключать устройства, управляемые Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="c3ca5-113">Эти отчеты интегрировали эту возможность фильтрации:</span><span class="sxs-lookup"><span data-stu-id="c3ca5-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="c3ca5-114">Все устройства</span><span class="sxs-lookup"><span data-stu-id="c3ca5-114">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="c3ca5-115">Соответствие устройства требованиям</span><span class="sxs-lookup"><span data-stu-id="c3ca5-115">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="c3ca5-116">Некомплиентные устройства</span><span class="sxs-lookup"><span data-stu-id="c3ca5-116">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="c3ca5-117">Настраиваемые роли управляемых настольных компьютеров Майкрософт гарантируют доступ только к отчетам Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="c3ca5-118">Чтобы получить доступ к другим частям Microsoft Endpoint Manager, таким как **Все** устройства, см. в этой ссылке управление доступом на основе ролей [с помощью Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="c3ca5-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="reports-in-microsoft-365-admin-center"></a><span data-ttu-id="c3ca5-119">Отчеты в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3ca5-119">Reports in Microsoft 365 Admin Center</span></span>

<span data-ttu-id="c3ca5-120">Вы можете найти отчеты о microsoft Managed Desktop, открыв Центр администрирования Microsoft  [365,](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)а затем перейдите к отчетам и выбрав microsoft **Managed Desktop.**</span><span class="sxs-lookup"><span data-stu-id="c3ca5-120">You can find Microsoft Managed Desktop insights reports by opening the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop), and then navigating to **Reports** and selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="c3ca5-121">Вы также можете следовать прямой ссылке на эти отчеты из **вкладки Microsoft Managed Desktop** на домашней странице [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c3ca5-121">You can also follow the direct link to these reports from the **Microsoft Managed Desktop** tab on the homepage [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span> 

<span data-ttu-id="c3ca5-122">Эти отчеты включают:</span><span class="sxs-lookup"><span data-stu-id="c3ca5-122">These reports include:</span></span> 

- <span data-ttu-id="c3ca5-123">[Сведения об использовании](usage-insights.md) . В этом представлении метрики использования для устройств Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-123">[Usage insights](usage-insights.md) - This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="c3ca5-124">[Сведения о надежности](reliability-insights.md) . В этом представлении содержится сводка о состоянии здоровья управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-124">[Reliability insights](reliability-insights.md) - This view provides you with a health summary of your managed devices.</span></span>
- <span data-ttu-id="c3ca5-125">[Сведения о батарее](battery-insights.md) . В этом представлении показано, как расход энергии приложений и прогнозируемый срок службы батареи для устройств в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-125">[Battery insights](battery-insights.md) - This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span>
- <span data-ttu-id="c3ca5-126">[Сведения об обновлении безопасности](security-update-insights.md) Windows . В этом представлении показаны сведения о состоянии обновлений безопасности для устройств Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-126">[Windows security update insights](security-update-insights.md) - This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="c3ca5-127">Данные инвентаризации</span><span class="sxs-lookup"><span data-stu-id="c3ca5-127">Inventory data</span></span>

<span data-ttu-id="c3ca5-128">Помимо других отчетов, можно экспортировать сведения о устройствах, управляемых Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c3ca5-128">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="c3ca5-129">В **представлении Устройств** области **Устройств** в Microsoft Endpoint Manager используйте вкладку Экспорт все, чтобы  [скачать подробный отчет о запасах.](device-inventory-report.md)</span><span class="sxs-lookup"><span data-stu-id="c3ca5-129">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>