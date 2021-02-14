---
title: Несовершеннолетних и приобретение надстройки в Магазине
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
description: Сведения о правилах Общего регламента по защите данных (GDPR), которые регулируют персональные данные несовершеннолетних.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306555"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="6c877-103">Несовершеннолетних и приобретение надстройки в Магазине</span><span class="sxs-lookup"><span data-stu-id="6c877-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="6c877-104">Общий регламент по защите данных (GDPR) — это нормативный акт Европейского союза, который в силу в силу в 25 мая 2018 г.</span><span class="sxs-lookup"><span data-stu-id="6c877-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="6c877-105">Она предоставляет пользователям права на доступ к их данным и защиту их данных.</span><span class="sxs-lookup"><span data-stu-id="6c877-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="6c877-106">Одним из аспектов GDPR является то, что несовершеннолетних не могут иметь свои персональные данные, отправленные сторонам, которые их родительский или опекун не утвержден.</span><span class="sxs-lookup"><span data-stu-id="6c877-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="6c877-107">Конкретный возраст, определенный как несовершеннолетних, зависит от региона, в котором находится человек.</span><span class="sxs-lookup"><span data-stu-id="6c877-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="6c877-108">К регионам, которые имеют нормативные акты о родительском согласии, относятся США, Южная Корея, Соединенное Королевство и Европейский союз.</span><span class="sxs-lookup"><span data-stu-id="6c877-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="6c877-109">Для этих регионов несовершеннолетних будет заблокировано (через Azure Active Directory) получать новые надстройки Office из Магазина и запускать ранее приобретенные надстройки.</span><span class="sxs-lookup"><span data-stu-id="6c877-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="6c877-110">Для стран без нормативных требований никакие ограничения на загрузку не действуют.</span><span class="sxs-lookup"><span data-stu-id="6c877-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="6c877-111">Пользователь определяется как несовершеннолетних на основе данных, указанных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c877-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="6c877-112">Администратор организации несет ответственность за объявление юридической возрастной группы и родительского согласия для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c877-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="6c877-113">Если родитель или опекун соглашается на несовершеннолетних с помощью определенной надстройки, администратор организации может использовать централизованное развертывание для развертывания этой надстройки для всех несовершеннолетних, которые имеют согласие.</span><span class="sxs-lookup"><span data-stu-id="6c877-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="6c877-114">Чтобы обеспечить соответствие требованиям GDPR для несовершеннолетних, необходимо убедиться, что одна из следующих сборков Office развернута в вашем учебном замещании или организации.</span><span class="sxs-lookup"><span data-stu-id="6c877-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="6c877-115">**Для Word, Excel, PowerPoint и Project:**</span><span class="sxs-lookup"><span data-stu-id="6c877-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="6c877-116">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="6c877-116">**Platform**</span></span> <br/> |<span data-ttu-id="6c877-117">**Номер сборки**</span><span class="sxs-lookup"><span data-stu-id="6c877-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="6c877-118">Приложения Microsoft 365 для предприятий (Current Channel)</span><span class="sxs-lookup"><span data-stu-id="6c877-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="6c877-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="6c877-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="6c877-120">Приложения Microsoft 365 для предприятий (Semi-Annual Enterprise Channel)</span><span class="sxs-lookup"><span data-stu-id="6c877-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="6c877-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="6c877-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="6c877-122">Office 2016 для Windows</span><span class="sxs-lookup"><span data-stu-id="6c877-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="6c877-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="6c877-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="6c877-124">Office 2013 для Windows</span><span class="sxs-lookup"><span data-stu-id="6c877-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="6c877-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="6c877-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="6c877-126">Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="6c877-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="6c877-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="6c877-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="6c877-128">Office в Интернете</span><span class="sxs-lookup"><span data-stu-id="6c877-128">Office for the web</span></span>  <br/> |<span data-ttu-id="6c877-129">Недоступно</span><span class="sxs-lookup"><span data-stu-id="6c877-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="6c877-130">**Для Outlook**:</span><span class="sxs-lookup"><span data-stu-id="6c877-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="6c877-131">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="6c877-131">**Platform**</span></span> <br/> |<span data-ttu-id="6c877-132">**Номер сборки**</span><span class="sxs-lookup"><span data-stu-id="6c877-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="6c877-133">Outlook 2016 для Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="6c877-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="6c877-134">Сборка без tbd</span><span class="sxs-lookup"><span data-stu-id="6c877-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="6c877-135">Outlook 2016 для Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="6c877-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="6c877-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="6c877-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="6c877-137">Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="6c877-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="6c877-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="6c877-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="6c877-139">Outlook Mobile для iOS</span><span class="sxs-lookup"><span data-stu-id="6c877-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="6c877-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="6c877-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="6c877-141">Outlook Mobile для Android</span><span class="sxs-lookup"><span data-stu-id="6c877-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="6c877-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="6c877-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="6c877-143">Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6c877-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="6c877-144">Недоступно</span><span class="sxs-lookup"><span data-stu-id="6c877-144">N/A</span></span>  <br/> |

 <span data-ttu-id="6c877-145">**Требования к Office 2013**</span><span class="sxs-lookup"><span data-stu-id="6c877-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="6c877-146">Word, Excel и PowerPoint 2013 для Windows будут поддерживать те же проверки несовершеннолетних, если включена библиотека проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="6c877-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="6c877-147">Существует два варианта обеспечения соответствия требованиям, как поясняется далее.</span><span class="sxs-lookup"><span data-stu-id="6c877-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="6c877-148">**Включить ADAL**.</span><span class="sxs-lookup"><span data-stu-id="6c877-148">**Enable ADAL**.</span></span> <span data-ttu-id="6c877-149">В этой статье объясняется, как включить ADAL для Office 2013: использование современной проверки подлинности [Microsoft 365 с клиентами Office.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="6c877-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="6c877-150">Кроме того, необходимо настроить ключи реестра, чтобы включить ADAL, как поясняется в подстройки "Включить современную проверку подлинности для [Office 2013" на устройствах с Windows.](../security-and-compliance/enable-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="6c877-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="6c877-151">Кроме того, необходимо установить следующие обновления для Office 2013 за апрель:</span><span class="sxs-lookup"><span data-stu-id="6c877-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="6c877-152">Описание обновления для системы безопасности Office 2013: 10 апреля 2018 г.</span><span class="sxs-lookup"><span data-stu-id="6c877-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="6c877-153">3 апреля 2018 г., обновление для Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="6c877-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="6c877-154">**Не в включается ADAL.**</span><span class="sxs-lookup"><span data-stu-id="6c877-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="6c877-155">Если вы не можете включить ADAL в Office 2013, мы вернемся с помощью групповой политики, чтобы отключить Магазин для клиентов Office.</span><span class="sxs-lookup"><span data-stu-id="6c877-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="6c877-156">Сведения о том, как отключить приложение для параметров Office, можно найти [здесь.](https://technet.microsoft.com/library/cc178992.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c877-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c877-157">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6c877-157">Related articles</span></span>

[<span data-ttu-id="6c877-158">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="6c877-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="6c877-159">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="6c877-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
