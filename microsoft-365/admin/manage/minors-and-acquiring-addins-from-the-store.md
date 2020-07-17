---
title: Вспомогательные и приобретение надстроек из магазина
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Узнайте о требованиях к общему законодательству по защите данных (GDPR), которые управляют личными данными вспомогательных элементов.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103120"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="091b7-103">Вспомогательные и приобретение надстроек из магазина</span><span class="sxs-lookup"><span data-stu-id="091b7-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="091b7-104">Общая норма защиты данных (GDPR) — это регламентирование Европейского союза, которое вступает в силу до 25 мая 2018 г.</span><span class="sxs-lookup"><span data-stu-id="091b7-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="091b7-105">Он предоставляет пользователям права и защиту своих данных.</span><span class="sxs-lookup"><span data-stu-id="091b7-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="091b7-106">Одним из аспектов GDPR является то, что небольшие данные не могут быть отправлены сторонам, которые не были утверждены их родительским или опекуном.</span><span class="sxs-lookup"><span data-stu-id="091b7-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="091b7-107">Определенный возраст, определенный как второстепенный, зависит от региона, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="091b7-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="091b7-108">Регионы, имеющие нормативные требования о доходе разрешения родителей, включают в себя США, Южная Корея, Великобритания и Европейского союза.</span><span class="sxs-lookup"><span data-stu-id="091b7-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="091b7-109">Для этих регионов дополнительный набор будет заблокирован (через Azure Active Directory) от получения новых надстроек Office из Store и запущенных ранее надстроек.</span><span class="sxs-lookup"><span data-stu-id="091b7-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="091b7-110">Для стран без нормативных нормативных ограничений отсутствуют ограничения на загрузку.</span><span class="sxs-lookup"><span data-stu-id="091b7-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="091b7-111">Определено, что пользователь является незначительным в зависимости от данных, указанных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="091b7-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="091b7-112">Администратор Организации несет ответственность за объявление законной возрастной группы и согласие пользователя на их родительский доступ.</span><span class="sxs-lookup"><span data-stu-id="091b7-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="091b7-113">Если родительский/опекун отсылается во вспомогательную надстройку с помощью определенной надстройки, администратор организации может использовать централизованное развертывание для развертывания этой надстройки во всех вспомогательных, у которых есть согласие.</span><span class="sxs-lookup"><span data-stu-id="091b7-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="091b7-114">Чтобы обеспечить GDPR требованиям к дополнительным значениям, необходимо убедиться в том, что в вашем учебном заведении или организации развернута одна из следующих сборок Office.</span><span class="sxs-lookup"><span data-stu-id="091b7-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="091b7-115">**Для Word, Excel, PowerPoint и Project**:</span><span class="sxs-lookup"><span data-stu-id="091b7-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="091b7-116">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="091b7-116">**Platform**</span></span> <br/> |<span data-ttu-id="091b7-117">**Номер сборки**</span><span class="sxs-lookup"><span data-stu-id="091b7-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="091b7-118">Приложения Microsoft 365 для предприятий (текущий канал)</span><span class="sxs-lookup"><span data-stu-id="091b7-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="091b7-119">9001,2138</span><span class="sxs-lookup"><span data-stu-id="091b7-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="091b7-120">Приложения Microsoft 365 для предприятий (полугодовой канал предприятия)</span><span class="sxs-lookup"><span data-stu-id="091b7-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="091b7-121">8431,2159</span><span class="sxs-lookup"><span data-stu-id="091b7-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="091b7-122">Office 2016 для Windows</span><span class="sxs-lookup"><span data-stu-id="091b7-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="091b7-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="091b7-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="091b7-124">Office 2013 для Windows</span><span class="sxs-lookup"><span data-stu-id="091b7-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="091b7-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="091b7-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="091b7-126">Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="091b7-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="091b7-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="091b7-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="091b7-128">Office в Интернете</span><span class="sxs-lookup"><span data-stu-id="091b7-128">Office for the web</span></span>  <br/> |<span data-ttu-id="091b7-129">Недоступно</span><span class="sxs-lookup"><span data-stu-id="091b7-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="091b7-130">**Для Outlook**:</span><span class="sxs-lookup"><span data-stu-id="091b7-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="091b7-131">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="091b7-131">**Platform**</span></span> <br/> |<span data-ttu-id="091b7-132">**Номер сборки**</span><span class="sxs-lookup"><span data-stu-id="091b7-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="091b7-133">Outlook 2016 для Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="091b7-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="091b7-134">Сборка не подлежит определению</span><span class="sxs-lookup"><span data-stu-id="091b7-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="091b7-135">Outlook 2016 для Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="091b7-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="091b7-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="091b7-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="091b7-137">Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="091b7-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="091b7-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="091b7-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="091b7-139">Outlook Mobile для iOS</span><span class="sxs-lookup"><span data-stu-id="091b7-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="091b7-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="091b7-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="091b7-141">Outlook Mobile для Android</span><span class="sxs-lookup"><span data-stu-id="091b7-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="091b7-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="091b7-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="091b7-143">Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="091b7-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="091b7-144">Недоступно</span><span class="sxs-lookup"><span data-stu-id="091b7-144">N/A</span></span>  <br/> |

 <span data-ttu-id="091b7-145">**Требования к Office 2013**</span><span class="sxs-lookup"><span data-stu-id="091b7-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="091b7-146">Word, Excel и PowerPoint 2013 для Windows будут поддерживать одни и те же небольшие проверки, если включена библиотека проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="091b7-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="091b7-147">Существует два варианта соответствия требованиям, как описано далее.</span><span class="sxs-lookup"><span data-stu-id="091b7-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="091b7-148">**Включите ADAL**.</span><span class="sxs-lookup"><span data-stu-id="091b7-148">**Enable ADAL**.</span></span> <span data-ttu-id="091b7-149">В этой статье объясняется, как включить ADAL для Office 2013: [использование современной проверки подлинности Microsoft 365 с клиентами Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span><span class="sxs-lookup"><span data-stu-id="091b7-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="091b7-150">Кроме того, необходимо настроить разделы реестра для включения ADAL, как описано в разделе [Включение современной проверки подлинности для Office 2013 на устройствах с Windows](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="091b7-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="091b7-151">Кроме того, необходимо установить следующие обновления за Апрель для Office 2013:</span><span class="sxs-lookup"><span data-stu-id="091b7-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="091b7-152">Описание обновления для системы безопасности для Office 2013:10 апреля 2018 г.</span><span class="sxs-lookup"><span data-stu-id="091b7-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="091b7-153">3 апреля 2018 г., обновление для Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="091b7-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="091b7-154">**Не ВКЛЮЧАЙТЕ ADAL**.</span><span class="sxs-lookup"><span data-stu-id="091b7-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="091b7-155">Если вы не можете включить ADAL в Office 2013, мы рекомендуем использовать групповую политику, чтобы отключить магазин для клиентов Office.</span><span class="sxs-lookup"><span data-stu-id="091b7-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="091b7-156">Сведения о том, как отключить параметры приложения для Office, находятся [здесь](https://technet.microsoft.com/library/cc178992.aspx).</span><span class="sxs-lookup"><span data-stu-id="091b7-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="091b7-157">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="091b7-157">Related articles</span></span>

[<span data-ttu-id="091b7-158">Развертывание надстроек в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="091b7-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="091b7-159">Управление надстройками в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="091b7-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
