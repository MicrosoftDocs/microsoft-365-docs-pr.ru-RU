---
title: Вопросы и ответы о централизованном развертывании
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
description: Просмотрите ответы на частые вопросы о централизованном развертывании из Центр администрирования Microsoft 365.
ms.openlocfilehash: 0da9ec9595fd433abe1e2e2ae3f2e3a0c6b3b9b5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228011"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="ff251-103">Вопросы и ответы о централизованном развертывании</span><span class="sxs-lookup"><span data-stu-id="ff251-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="ff251-104">Централизованное развертывание — это рекомендуемый способ для администратора Office 365 развертывания надстройок Office (Word, Excel, PowerPoint и Outlook) для пользователей и групп в организации при условии, что организация отвечает всем требованиям по использованию централизованного развертывания, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ff251-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="ff251-105">Как узнать, настроена ли моя организация для централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="ff251-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="ff251-106">Централизованное развертывание надстройок требует, чтобы пользователи использовали Приложения Microsoft 365 для предприятий (и подписывался в Office с помощью учетных данных для входа в организацию) и Exchange Online почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="ff251-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="ff251-107">Каталог подписки должен быть либо в каталоге, либо в федерате, Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff251-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="ff251-108">Централизованное развертывание поддерживается только для почтовых ящиков в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ff251-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="ff251-109">Он не поддерживает развертывание в Exchange почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="ff251-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="ff251-110">Чтобы определить, [](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)имеет ли ваша подписка право на подписку, можно использовать централизованную проверку совместимости   развертывания.</span><span class="sxs-lookup"><span data-stu-id="ff251-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="ff251-111">Как нацелить назначения пользователей надстройки с помощью централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="ff251-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="ff251-112">Централизованное развертывание поддерживает назначения отдельным пользователям, группам и всем пользователям в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ff251-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="ff251-113">Централизованное развертывание можно использовать для пользователей в группах верхнего уровня или группах без родительских групп, но не для пользователей в вложенных группах или группах с родительскими группами.</span><span class="sxs-lookup"><span data-stu-id="ff251-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="ff251-114">Централизованное развертывание также является частью большинства Azure Active Directory, включая группы Office 365, списки рассылки и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ff251-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="ff251-115">Для более простого управления лучше использовать назначения групп, а не отдельные назначения пользователей.</span><span class="sxs-lookup"><span data-stu-id="ff251-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="ff251-116">Дополнительные сведения см. в [материале User and Group assignments.](./centralized-deployment-of-add-ins.md#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="ff251-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="ff251-117">Сколько времени займет показ надстройки для всех пользователей?</span><span class="sxs-lookup"><span data-stu-id="ff251-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="ff251-118">Для показа надстройки для всех пользователей может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="ff251-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="ff251-119">Это может занять одинаковое время для обновлений надстройки, изменений при включите или отключите или удалите надстройки.</span><span class="sxs-lookup"><span data-stu-id="ff251-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="ff251-120">Как администратору управлять доступом пользователей к надстройки для моей организации?</span><span class="sxs-lookup"><span data-stu-id="ff251-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="ff251-121">Для простого развертывания надстройок для пользователей, групп или всей организации рекомендуем администраторам использовать централизованное развертывание.</span><span class="sxs-lookup"><span data-stu-id="ff251-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="ff251-122">Дополнительные сведения об управлении доступом пользователей см. в этой записи.</span><span class="sxs-lookup"><span data-stu-id="ff251-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="ff251-123">Предотвращение скачивания надстройки путем отключения Office магазина для всех клиентов (кроме Outlook)</span><span class="sxs-lookup"><span data-stu-id="ff251-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="ff251-124">Выбор администраторов и пользователей, которые могут устанавливать надстройки для Outlook и управлять ими</span><span class="sxs-lookup"><span data-stu-id="ff251-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="ff251-125">Будет ли централизованное развертывание предоставлять администраторам гибкость при выборе метода развертывания для Outlook надстройки?</span><span class="sxs-lookup"><span data-stu-id="ff251-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="ff251-126">Да.</span><span class="sxs-lookup"><span data-stu-id="ff251-126">Yes.</span></span> <span data-ttu-id="ff251-127">Централизованное развертывание предоставляет администраторам возможность выбора одного из трех методов развертывания для Outlook надстройки во время развертывания надстройки:</span><span class="sxs-lookup"><span data-stu-id="ff251-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="ff251-128">**Исправлено (по умолчанию)**   Надстройка развертывается автоматически для назначенного пользователя, и они не могут удалить его.</span><span class="sxs-lookup"><span data-stu-id="ff251-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="ff251-129">**Доступно** Пользователи могут установить надстройку в Outlook, выбрав home > Получить больше надстройок > **администрирования.**</span><span class="sxs-lookup"><span data-stu-id="ff251-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="ff251-130">**Необязательный** Надстройка развертывается автоматически для назначенного пользователя, но они могут удалить его.</span><span class="sxs-lookup"><span data-stu-id="ff251-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="ff251-131">Могут ли администраторы обновлять надстройки Line-of-Business (LOB)?</span><span class="sxs-lookup"><span data-stu-id="ff251-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="ff251-132">Да.</span><span class="sxs-lookup"><span data-stu-id="ff251-132">Yes.</span></span> <span data-ttu-id="ff251-133">Администраторы могут загружать новый файл манифеста для поддержки изменений метаданных для надстройок LOB, развернутых администратором. Надстройка обновляется при следующем Office приложений.</span><span class="sxs-lookup"><span data-stu-id="ff251-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="ff251-134">Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="ff251-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="ff251-135">Дополнительные сведения см. [в добавлении line-of-business.](./manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="ff251-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="ff251-136">Могут ли администраторы отключить надстройки?</span><span class="sxs-lookup"><span data-stu-id="ff251-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="ff251-137">Да.</span><span class="sxs-lookup"><span data-stu-id="ff251-137">Yes.</span></span> <span data-ttu-id="ff251-138">Администраторы могут включить или отключить развернутые надстройки для всех пользователей центра администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ff251-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="ff251-139">Дополнительные сведения см. [в дополнительных сведениях о состояниях надстройки.](./manage-addins-in-the-admin-center.md#add-in-states)</span><span class="sxs-lookup"><span data-stu-id="ff251-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="ff251-140">Могут ли администраторы удалять или удалять надстройки?</span><span class="sxs-lookup"><span data-stu-id="ff251-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="ff251-141">Да.</span><span class="sxs-lookup"><span data-stu-id="ff251-141">Yes.</span></span> <span data-ttu-id="ff251-142">Администраторы могут удалять надстройки, развернутые для всех пользователей из центра администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ff251-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="ff251-143">Дополнительные сведения см. в [публикации Delete an add-in.](./manage-addins-in-the-admin-center.md#delete-an-add-in)</span><span class="sxs-lookup"><span data-stu-id="ff251-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="ff251-144">Могут ли администраторы развертывать платные надстройки из магазина Office с помощью централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="ff251-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="ff251-145">Нет.</span><span class="sxs-lookup"><span data-stu-id="ff251-145">No.</span></span> <span data-ttu-id="ff251-146">Вы не можете развернуть платные надстройки из магазина Office с помощью централизованного развертывания в это время.</span><span class="sxs-lookup"><span data-stu-id="ff251-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="ff251-147">Мы предлагаем связаться с разработчиком ISV для платной надстройки, чтобы запросить файл манифеста или URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="ff251-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="ff251-148">Затем администратор клиента может развернуть надстройку в качестве надстройки LOB с помощью централизированного развертывания.</span><span class="sxs-lookup"><span data-stu-id="ff251-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="ff251-149">Какая роль администратора мне нужна для управления надстройки для моей организации?</span><span class="sxs-lookup"><span data-stu-id="ff251-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="ff251-150">Глобальный администратор — это рекомендуемая роль с полным доступом к жизненному циклу управления надстройки.</span><span class="sxs-lookup"><span data-stu-id="ff251-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="ff251-151">Если вы приобрели подписку Microsoft 365 бизнеса, вы — глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="ff251-151">If you're the person who purchased your Microsoft 365 Business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="ff251-152">Подписка поставляется с набором ролей администратора, которые можно назначить другим пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="ff251-152">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="ff251-153">Каждая роль администратора передает общие бизнес-функции и дает людям в организации разрешения на выполнение определенных задач в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff251-153">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="ff251-154">Дополнительные сведения см. в [дополнительных сведениях о назначении ролей администратора.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ff251-154">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md).</span></span> 
