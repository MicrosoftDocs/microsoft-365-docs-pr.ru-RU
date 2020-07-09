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
description: Ознакомьтесь с ответами на часто задаваемые вопросы о централизованном развертывании в центре администрирования Microsoft 365.
ms.openlocfilehash: 2d9a3c6f2cfe9418cc83cbd0f29537e5533c4257
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083566"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="b81a3-103">Вопросы и ответы о централизованном развертывании</span><span class="sxs-lookup"><span data-stu-id="b81a3-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="b81a3-104">Централизованное развертывание — рекомендуемый 365 способ развертывания надстроек Office (Word, Excel, PowerPoint и Outlook) для пользователей и групп в Организации при условии, что организация отвечает всем требованиям для использования централизованного развертывания, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b81a3-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="b81a3-105">Как узнать, настроена ли Организация для централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="b81a3-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="b81a3-106">Для централизованного развертывания надстроек необходимо, чтобы пользователи выполняли приложения Microsoft 365 для предприятий (и вошли в Office с помощью учетных данных Организации) и иметь почтовые ящики Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b81a3-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="b81a3-107">Каталог подписки должен находиться в службе Azure Active Directory или быть Федеративной для нее.</span><span class="sxs-lookup"><span data-stu-id="b81a3-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="b81a3-108">Централизованное развертывание поддерживается только для веб-почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="b81a3-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="b81a3-109">Он не поддерживает развертывание для локальных почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="b81a3-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>
 
<span data-ttu-id="b81a3-110">Можно использовать [средство проверки совместимости централизованного развертывания](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker),   чтобы определить, подходит ли ваша подписка.</span><span class="sxs-lookup"><span data-stu-id="b81a3-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="b81a3-111">Как вы научитесь назначать пользователя надстройки при централизованном развертывании?</span><span class="sxs-lookup"><span data-stu-id="b81a3-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="b81a3-112">Централизованное развертывание поддерживает назначения для отдельных пользователей, групп и всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="b81a3-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="b81a3-113">Централизованное развертывание можно использовать для пользователей в группах или группах верхнего уровня без родительских групп, но не для пользователей в вложенных группах или группах с родительскими группами.</span><span class="sxs-lookup"><span data-stu-id="b81a3-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="b81a3-114">Централизованное развертывание также является частью большинства групп Azure Active Directory, в том числе групп Office 365, списков рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="b81a3-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="b81a3-115">Для упрощения управления лучше использовать назначения групп, а не индивидуальные назначения пользователей.</span><span class="sxs-lookup"><span data-stu-id="b81a3-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="b81a3-116">Более подробную информацию можно узнать в разделе [Назначение пользователей и групп](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="b81a3-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="b81a3-117">Сколько времени занимает надстройки для отображения для всех пользователей?</span><span class="sxs-lookup"><span data-stu-id="b81a3-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="b81a3-118">Для отображения надстройки для всех пользователей может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="b81a3-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="b81a3-119">Это может занять то же время для обновлений надстроек, изменения, внесенные после включения или отключения, или удаления надстроек.</span><span class="sxs-lookup"><span data-stu-id="b81a3-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="b81a3-120">Как администратор, как управлять доступом пользователей к надстройкам для моей организации?</span><span class="sxs-lookup"><span data-stu-id="b81a3-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="b81a3-121">Для упрощения развертывания надстроек для пользователей, групп или всей Организации мы рекомендуем администраторам использовать централизованное развертывание.</span><span class="sxs-lookup"><span data-stu-id="b81a3-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="b81a3-122">Более подробную информацию об управлении доступом пользователей можно узнать в статье</span><span class="sxs-lookup"><span data-stu-id="b81a3-122">For more information about managing user access, see</span></span> </br><span data-ttu-id="b81a3-123">[Запретить загрузку надстроек, отключив магазин Office для всех клиентов (кроме Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) и</span><span class="sxs-lookup"><span data-stu-id="b81a3-123">[Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) and</span></span> </br><span data-ttu-id="b81a3-124">[Укажите администраторов и пользователей, которые могут устанавливать надстройки для Outlook и управлять ими](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span><span class="sxs-lookup"><span data-stu-id="b81a3-124">[Specify the administrators and users who can install and manage add-ins for Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span></span>

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="b81a3-125">Централизованное развертывание позволяет администраторам выбрать способ развертывания надстроек Outlook?</span><span class="sxs-lookup"><span data-stu-id="b81a3-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="b81a3-126">Да.</span><span class="sxs-lookup"><span data-stu-id="b81a3-126">Yes.</span></span> <span data-ttu-id="b81a3-127">Централизованное развертывание предоставляет администраторам гибкие возможности выбора одного из трех методов развертывания надстроек Outlook во время развертывания надстройки:</span><span class="sxs-lookup"><span data-stu-id="b81a3-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="b81a3-128">**Фиксированный (по умолчанию)**   Надстройка автоматически развертывается для назначенных пользователей и не может удаляться.</span><span class="sxs-lookup"><span data-stu-id="b81a3-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="b81a3-129">**Доступен** Пользователи могут установить надстройку в Outlook, выбрав пункт Домашняя > получить другие надстройки > управляемые администратором.</span><span class="sxs-lookup"><span data-stu-id="b81a3-129">**Available** Users can install the add-in in Outlook by choosing Home > Get More add-ins > Admin-managed.</span></span>   
 
<span data-ttu-id="b81a3-130">**Необязательное требование** Надстройка автоматически развертывается для назначенных пользователей, но может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="b81a3-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="b81a3-131">Могут администраторы обновлять бизнес-надстройки?</span><span class="sxs-lookup"><span data-stu-id="b81a3-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="b81a3-132">Да.</span><span class="sxs-lookup"><span data-stu-id="b81a3-132">Yes.</span></span> <span data-ttu-id="b81a3-133">Администраторы могут отправлять новый файл манифеста для поддержки изменений метаданных для специализированных надстроек, развернутых администратором. Надстройка обновится при следующем запуске приложений Office.</span><span class="sxs-lookup"><span data-stu-id="b81a3-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="b81a3-134">Веб-приложение может изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="b81a3-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="b81a3-135">Более подробную информацию можно узнать [в статье надстройка для бизнеса](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="b81a3-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="b81a3-136">Могут администраторы отключить надстройки?</span><span class="sxs-lookup"><span data-stu-id="b81a3-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="b81a3-137">Да.</span><span class="sxs-lookup"><span data-stu-id="b81a3-137">Yes.</span></span> <span data-ttu-id="b81a3-138">Администраторы могут включать и отключать надстройки, которые они развертывают, для всех пользователей в центре администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b81a3-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="b81a3-139">Дополнительную информацию можно узнать [в статье состояния надстроек](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="b81a3-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="b81a3-140">Могут ли администраторы удалять или удалять надстройки?</span><span class="sxs-lookup"><span data-stu-id="b81a3-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="b81a3-141">Да.</span><span class="sxs-lookup"><span data-stu-id="b81a3-141">Yes.</span></span> <span data-ttu-id="b81a3-142">Администраторы могут удалять надстройки, развернутые для всех пользователей в центре администрирования Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b81a3-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="b81a3-143">Дополнительные сведения см. [в статье удаление надстройки](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span><span class="sxs-lookup"><span data-stu-id="b81a3-143">For more information, see [Delete the add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="b81a3-144">Могут администраторы развертывать платные надстройки из магазина Office с помощью централизованного развертывания?</span><span class="sxs-lookup"><span data-stu-id="b81a3-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="b81a3-145">Нет.</span><span class="sxs-lookup"><span data-stu-id="b81a3-145">No.</span></span> <span data-ttu-id="b81a3-146">В настоящее время вы не можете развернуть платные надстройки из магазина Office с помощью централизованного развертывания.</span><span class="sxs-lookup"><span data-stu-id="b81a3-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="b81a3-147">Мы рекомендуем вам присвоить поставщику программного обеспечения для платной надстройки запрос файла манифеста или URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b81a3-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="b81a3-148">После этого администратор клиента может развернуть надстройку в виде бизнес-надстройки с помощью централизованного развертывания.</span><span class="sxs-lookup"><span data-stu-id="b81a3-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="b81a3-149">Какую роль администратора требуется для управления надстройками в Организации?</span><span class="sxs-lookup"><span data-stu-id="b81a3-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="b81a3-150">Для управления надстройками необходимо иметь роль глобального администратора. Если вы человек, который приобрели подписку на Microsoft 365 для бизнеса, вы являетесь глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="b81a3-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="b81a3-151">Ваша подписка сопровождается набором ролей администратора, которые можно назначить другим пользователям в Организации.</span><span class="sxs-lookup"><span data-stu-id="b81a3-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="b81a3-152">Каждая роль администратора соответствует распространенным бизнес-функциям и предоставляет пользователям в организации разрешения на выполнение определенных задач в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b81a3-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="b81a3-153">Более подробную информацию можно узнать в статье [назначение ролей администратора](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b81a3-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  