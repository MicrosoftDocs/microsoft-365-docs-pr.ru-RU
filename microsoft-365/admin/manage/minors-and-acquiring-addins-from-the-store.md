---
title: Несовершеннолетние и приобретение надстройок из Магазина
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Сведения о правилах общего регулирования защиты данных (GDPR), которые регулируют персональные данные несовершеннолетних.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580922"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="33adc-103">Несовершеннолетние и приобретение надстройок из Магазина</span><span class="sxs-lookup"><span data-stu-id="33adc-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="33adc-104">Правило общей защиты данных (GDPR) — это регулирование Европейского союза, которое в силу в силу в конце 2018 г. в конце 2018 г.</span><span class="sxs-lookup"><span data-stu-id="33adc-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="33adc-105">Это дает пользователям права на и защиту своих данных.</span><span class="sxs-lookup"><span data-stu-id="33adc-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="33adc-106">Одним из аспектов GDPR является то, что несовершеннолетние не могут отправить свои персональные данные сторонам, которые не утверждены их родителем или опекуном.</span><span class="sxs-lookup"><span data-stu-id="33adc-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="33adc-107">Определенный возраст, определенный как несовершеннолетний, зависит от региона, в котором находится человек.</span><span class="sxs-lookup"><span data-stu-id="33adc-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="33adc-108">Регионы с нормативными положениями о родительском согласии включают Соединенные Штаты, Южную Корею, Соединенное Королевство и Европейский союз.</span><span class="sxs-lookup"><span data-stu-id="33adc-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="33adc-109">Для этих регионов несовершеннолетний будет заблокирован (Azure Active Directory) от получения новых надстройок Office из Магазина и запущенных надстройок, которые были приобретены ранее.</span><span class="sxs-lookup"><span data-stu-id="33adc-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="33adc-110">Для стран без нормативных положений ограничения на загрузку не будут.</span><span class="sxs-lookup"><span data-stu-id="33adc-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="33adc-111">Пользователь определяется как несовершеннолетний на основе данных, указанных в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="33adc-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="33adc-112">Администратор организации отвечает за объявление юридической возрастной группы и родительского согласия для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="33adc-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="33adc-113">Если родитель/опекун соглашается на несовершеннолетнего с помощью определенной надстройки, администратор организации может использовать централизованное развертывание для развертывания этой надстройки для всех несовершеннолетних, у которых есть согласие.</span><span class="sxs-lookup"><span data-stu-id="33adc-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="33adc-114">Чтобы быть совместимым с GDPR для несовершеннолетних, необходимо убедиться, что одна из следующих сборки Office развернута в вашей школе или организации.</span><span class="sxs-lookup"><span data-stu-id="33adc-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="33adc-115">**Для Word, Excel, PowerPoint и Project:**</span><span class="sxs-lookup"><span data-stu-id="33adc-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="33adc-116">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="33adc-116">**Platform**</span></span> <br/> |<span data-ttu-id="33adc-117">**Номер сборки**</span><span class="sxs-lookup"><span data-stu-id="33adc-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="33adc-118">Приложения Microsoft 365 для предприятий (текущий канал)</span><span class="sxs-lookup"><span data-stu-id="33adc-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="33adc-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="33adc-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="33adc-120">Приложения Microsoft 365 для предприятий (полугодовой Enterprise канал)</span><span class="sxs-lookup"><span data-stu-id="33adc-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="33adc-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="33adc-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="33adc-122">Office 2016 для Windows</span><span class="sxs-lookup"><span data-stu-id="33adc-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="33adc-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="33adc-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="33adc-124">Office 2013 для Windows</span><span class="sxs-lookup"><span data-stu-id="33adc-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="33adc-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="33adc-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="33adc-126">Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="33adc-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="33adc-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="33adc-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="33adc-128">Office в Интернете</span><span class="sxs-lookup"><span data-stu-id="33adc-128">Office for the web</span></span>  <br/> |<span data-ttu-id="33adc-129">Н/Д</span><span class="sxs-lookup"><span data-stu-id="33adc-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="33adc-130">**Для Outlook:**</span><span class="sxs-lookup"><span data-stu-id="33adc-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="33adc-131">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="33adc-131">**Platform**</span></span> <br/> |<span data-ttu-id="33adc-132">**Номер сборки**</span><span class="sxs-lookup"><span data-stu-id="33adc-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="33adc-133">Outlook 2016 для Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="33adc-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="33adc-134">Сборка без TBD</span><span class="sxs-lookup"><span data-stu-id="33adc-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="33adc-135">Outlook 2016 для Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="33adc-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="33adc-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="33adc-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="33adc-137">Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="33adc-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="33adc-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="33adc-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="33adc-139">Outlook для iOS</span><span class="sxs-lookup"><span data-stu-id="33adc-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="33adc-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="33adc-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="33adc-141">Outlook для Android</span><span class="sxs-lookup"><span data-stu-id="33adc-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="33adc-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="33adc-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="33adc-143">Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="33adc-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="33adc-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="33adc-144">N/A</span></span>  <br/> |

 <span data-ttu-id="33adc-145">**Office 2013 г.**</span><span class="sxs-lookup"><span data-stu-id="33adc-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="33adc-146">Word, Excel и PowerPoint 2013 для Windows будут поддерживать те же проверки несовершеннолетних, если включена библиотека проверки подлинности Active Directory (ADAL).</span><span class="sxs-lookup"><span data-stu-id="33adc-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="33adc-147">Существует два варианта соответствия требованиям, как поясняется далее.</span><span class="sxs-lookup"><span data-stu-id="33adc-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="33adc-148">**Включить ADAL**.</span><span class="sxs-lookup"><span data-stu-id="33adc-148">**Enable ADAL**.</span></span> <span data-ttu-id="33adc-149">В этой статье рассказывается о том, как включить ADAL для Office 2013 г. Использование Microsoft 365 проверки подлинности с [Office клиентами.](../../enterprise/modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="33adc-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="33adc-150">Кроме того, необходимо настроить ключи реестра, чтобы включить ADAL, как поясняется в "Включить современную проверку подлинности для Office [2013](../security-and-compliance/enable-modern-authentication.md)г. на Windows устройствах.</span><span class="sxs-lookup"><span data-stu-id="33adc-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="33adc-151">Кроме того, необходимо установить следующие апрельские обновления для Office 2013 г.:</span><span class="sxs-lookup"><span data-stu-id="33adc-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="33adc-152">Описание обновления безопасности за Office 2013 г.: 10 апреля 2018 г.</span><span class="sxs-lookup"><span data-stu-id="33adc-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="33adc-153">3 апреля 2018 г., обновление за Office 2013 г. (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="33adc-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="33adc-154">**Не внося ADAL**.</span><span class="sxs-lookup"><span data-stu-id="33adc-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="33adc-155">Если вы не можете включить ADAL в Office 2013 г., то мы едим использовать групповую политику для отключения Магазина для Office клиентов.</span><span class="sxs-lookup"><span data-stu-id="33adc-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="33adc-156">Сведения о том, как отключить приложение для Office параметров, размещены [здесь](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="33adc-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="33adc-157">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="33adc-157">Related articles</span></span>

[<span data-ttu-id="33adc-158">Развертывание надстроек в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="33adc-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="33adc-159">Управление надстройками в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="33adc-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
