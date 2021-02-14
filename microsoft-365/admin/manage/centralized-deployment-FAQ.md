---
title: Вопросы и ответы о централизованном развертывании
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
description: Ответы на часто задающие вопросы о централизованном развертывании в Центре администрирования Microsoft 365.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948692"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="b2673-103">Вопросы и ответы о централизованном развертывании</span><span class="sxs-lookup"><span data-stu-id="b2673-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="b2673-104">Централизованное развертывание — это рекомендуемый способ для администратора Office 365 развернуть надстройки Office (Word, Excel, PowerPoint и Outlook) для пользователей и групп в организации при условии, что организация соответствует всем требованиям для использования централизованного развертывания, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b2673-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="b2673-105">Как узнать, настроена ли моя организация для централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="b2673-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="b2673-106">Для централизованного развертывания надстройки необходимо, чтобы пользователи использовали приложения Microsoft 365 для предприятий (и они вписались в Office с помощью учетных данных для входа в организацию) и использовали почтовые ящики Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b2673-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="b2673-107">Каталог подписки должен быть либо в Azure Active Directory, либо в федерате.</span><span class="sxs-lookup"><span data-stu-id="b2673-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="b2673-108">Централизованное развертывание поддерживается только для почтовых ящиков в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b2673-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="b2673-109">Развертывание в почтовых ящиках локальной системы Exchange не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b2673-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="b2673-110">Вы можете использовать [проверку](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)совместимости централизованного развертывания,   чтобы определить, имеет ли ваша подписка право на использование.</span><span class="sxs-lookup"><span data-stu-id="b2673-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="b2673-111">Как вы можете нацелить назначения пользователей надстройки с помощью централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="b2673-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="b2673-112">Централизованное развертывание поддерживает назначения отдельным пользователям, группам и всем пользователям в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b2673-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="b2673-113">Централизованное развертывание можно использовать для пользователей в группах верхнего уровня или группах без родительских групп, но не для пользователей во вложенных группах или группах с родительскими группами.</span><span class="sxs-lookup"><span data-stu-id="b2673-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="b2673-114">Централизованное развертывание также входит в большинство групп Azure Active Directory, включая группы Office 365, списки рассылки и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b2673-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="b2673-115">Для упростить управление лучше использовать назначения групп, а не назначение отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2673-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="b2673-116">Дополнительные сведения см. в [сведениях о назначениях пользователей и групп.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="b2673-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="b2673-117">Сколько времени займет показ надстройки для всех пользователей?</span><span class="sxs-lookup"><span data-stu-id="b2673-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="b2673-118">Чтобы надстройка отылалась для всех пользователей, может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="b2673-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="b2673-119">Обновление надстройки, изменения при включлении или отключлении, а также удаление надстройки может занять одинаковое время.</span><span class="sxs-lookup"><span data-stu-id="b2673-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="b2673-120">Как администратору управлять доступом пользователей к надстройки в моей организации?</span><span class="sxs-lookup"><span data-stu-id="b2673-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="b2673-121">Для простого развертывания надстройки для пользователей, групп или всей организации мы рекомендуем администраторам использовать централизованное развертывание.</span><span class="sxs-lookup"><span data-stu-id="b2673-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="b2673-122">Дополнительные сведения об управлении доступом пользователей см. в:</span><span class="sxs-lookup"><span data-stu-id="b2673-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="b2673-123">Запретить загрузку надстройки, отключив Магазин Office для всех клиентов (кроме Outlook)</span><span class="sxs-lookup"><span data-stu-id="b2673-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="b2673-124">Выбор администраторов и пользователей, которые могут устанавливать надстройки для Outlook и управлять ими</span><span class="sxs-lookup"><span data-stu-id="b2673-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="b2673-125">Будет ли централизованное развертывание предоставлять администраторам гибкость при выборе метода развертывания для надстройки Outlook?</span><span class="sxs-lookup"><span data-stu-id="b2673-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="b2673-126">Да.</span><span class="sxs-lookup"><span data-stu-id="b2673-126">Yes.</span></span> <span data-ttu-id="b2673-127">Централизованное развертывание позволяет администраторам выбрать один из трех способов развертывания надстройки Outlook во время развертывания надстройки:</span><span class="sxs-lookup"><span data-stu-id="b2673-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="b2673-128">**Фиксированный (по умолчанию)**   Надстройка развертывается автоматически для пользователей, и они не могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="b2673-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="b2673-129">**Доступно** Пользователи могут установить надстройку в Outlook, выбрав "Главная> Получить дополнительные надстройки> **управляемые администратором.**</span><span class="sxs-lookup"><span data-stu-id="b2673-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="b2673-130">**Необязательный** Надстройка развертывается автоматически для пользователей, которые назначены, но они могут удалить ее.</span><span class="sxs-lookup"><span data-stu-id="b2673-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="b2673-131">Могут ли администраторы обновлять бизнес-надстройки?</span><span class="sxs-lookup"><span data-stu-id="b2673-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="b2673-132">Да.</span><span class="sxs-lookup"><span data-stu-id="b2673-132">Yes.</span></span> <span data-ttu-id="b2673-133">Администраторы могут отправить новый файл манифеста для поддержки изменений метаданных для надстройки LOB, развернутых администратором. Надстройка обновляется при следующем старте приложений Office.</span><span class="sxs-lookup"><span data-stu-id="b2673-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="b2673-134">Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="b2673-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="b2673-135">Дополнительные сведения см. в [бизнес-надстройки.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)</span><span class="sxs-lookup"><span data-stu-id="b2673-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="b2673-136">Могут ли администраторы отключить надстройки?</span><span class="sxs-lookup"><span data-stu-id="b2673-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="b2673-137">Да.</span><span class="sxs-lookup"><span data-stu-id="b2673-137">Yes.</span></span> <span data-ttu-id="b2673-138">Администраторы могут включить или отключить развернутые надстройки для всех пользователей в Центре администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2673-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="b2673-139">Дополнительные сведения см. в [состояниях надстройки.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)</span><span class="sxs-lookup"><span data-stu-id="b2673-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="b2673-140">Могут ли администраторы удалять надстройки?</span><span class="sxs-lookup"><span data-stu-id="b2673-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="b2673-141">Да.</span><span class="sxs-lookup"><span data-stu-id="b2673-141">Yes.</span></span> <span data-ttu-id="b2673-142">Администраторы могут удалять надстройки, развернутые для всех пользователей, из Центра администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b2673-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="b2673-143">Дополнительные сведения см. [в подстройки "Удаление".](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in)</span><span class="sxs-lookup"><span data-stu-id="b2673-143">For more information, see [Delete an add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="b2673-144">Могут ли администраторы развертывать платные надстройки из Магазина Office с помощью централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="b2673-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="b2673-145">Нет.</span><span class="sxs-lookup"><span data-stu-id="b2673-145">No.</span></span> <span data-ttu-id="b2673-146">В настоящее время нельзя развернуть платные надстройки из Магазина Office с помощью централизованного развертывания.</span><span class="sxs-lookup"><span data-stu-id="b2673-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="b2673-147">Мы рекомендуем связаться с разработчиком для платной надстройки, чтобы запросить файл манифеста или URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="b2673-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="b2673-148">Затем администратор клиента может развернуть надстройку в качестве бизнес-надстройки с помощью централизованного развертывания.</span><span class="sxs-lookup"><span data-stu-id="b2673-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="b2673-149">Какая роль администратора требуется для управления надстройкими в моей организации?</span><span class="sxs-lookup"><span data-stu-id="b2673-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="b2673-150">Роль глобального администратора с полным доступом к жизненному циклу управления надстройки.</span><span class="sxs-lookup"><span data-stu-id="b2673-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="b2673-151">Другие роли администратора имеют ограниченный доступ к жизненному циклу развертывания надстройки.</span><span class="sxs-lookup"><span data-stu-id="b2673-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="b2673-152">Если вы приобрели подписку на Microsoft 365 для бизнеса, вы глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="b2673-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="b2673-153">Ваша подписка поставляется с набором ролей администратора, которые можно назначить другим пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="b2673-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="b2673-154">Каждая роль администратора сопопоает с общими бизнес-функциями и предоставляет людям в вашей организации разрешения на выполнение определенных задач в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2673-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="b2673-155">Дополнительные сведения см. в [под этой теме.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="b2673-155">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  


