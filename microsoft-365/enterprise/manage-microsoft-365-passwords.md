---
title: Управление Microsoft 365 паролями учетных записей пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Узнайте, как управлять паролями Microsoft 365 учетных записей пользователей.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905096"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="636be-103">Управление Microsoft 365 паролями учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="636be-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="636be-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="636be-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="636be-105">Вы можете управлять Microsoft 365 паролями учетных записей пользователей несколькими способами, в зависимости от конфигурации удостоверения.</span><span class="sxs-lookup"><span data-stu-id="636be-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="636be-106">Вы можете управлять учетными записями пользователей в центре [администрирования Microsoft 365,](../admin/add-users/index.yml)в службе домена Active Directory (AD DS) или в центре администрирования Azure Active Directory Azure AD.</span><span class="sxs-lookup"><span data-stu-id="636be-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="636be-107">Планирование, где и как вы будете управлять паролями учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="636be-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="636be-108">Где и как можно управлять учетной записью пользователя, зависит от модели удостоверений, используемой для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="636be-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="636be-109">Эти две модели являются облачными и гибридными.</span><span class="sxs-lookup"><span data-stu-id="636be-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="636be-110">Только облако</span><span class="sxs-lookup"><span data-stu-id="636be-110">Cloud-only</span></span>

<span data-ttu-id="636be-111">Вы управляете паролями учетных записей пользователей в:</span><span class="sxs-lookup"><span data-stu-id="636be-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="636be-112">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="636be-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="636be-113">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="636be-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="636be-114">Гибридная среда</span><span class="sxs-lookup"><span data-stu-id="636be-114">Hybrid</span></span>

<span data-ttu-id="636be-115">При гибридной идентификации пароли хранятся в AD DS, поэтому для управления паролями учетных записей пользователей необходимо использовать локальное оборудование AD DS.</span><span class="sxs-lookup"><span data-stu-id="636be-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="636be-116">Даже при использовании синхронизации с hash password (PHS), в которой Azure AD хранит hashed версию уже схронизированной версии в AD DS, вы и пользователи должны управлять своими паролями в AD DS.</span><span class="sxs-lookup"><span data-stu-id="636be-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="636be-117">При [списывке](#pw_writeback)паролей пользователи могут изменять свои пароли AD DS через Azure AD.</span><span class="sxs-lookup"><span data-stu-id="636be-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="636be-118">Запрет слабых паролей</span><span class="sxs-lookup"><span data-stu-id="636be-118">Prevent bad passwords</span></span>

<span data-ttu-id="636be-119">Все ваши пользователи должны применять [Руководство по паролям корпорации Майкрософт](https://www.microsoft.com/research/publication/password-guidance) для создания своих паролей учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="636be-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="636be-120">Чтобы запретить пользователям создавать легко подбираемые пароли, применяйте службу защиты паролей Azure AD, в которой используется как глобальный список запрещенных паролей, так и необязательный настраиваемый список запрещенных паролей, указываемый вами.</span><span class="sxs-lookup"><span data-stu-id="636be-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="636be-121">Например, вы можете указать следующие термины, относящиеся к вашей организации:</span><span class="sxs-lookup"><span data-stu-id="636be-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="636be-122">Фирменные названия</span><span class="sxs-lookup"><span data-stu-id="636be-122">Brand names</span></span>
- <span data-ttu-id="636be-123">Названия продуктов</span><span class="sxs-lookup"><span data-stu-id="636be-123">Product names</span></span>
- <span data-ttu-id="636be-124">Расположения (например, штаб-квартира компании)</span><span class="sxs-lookup"><span data-stu-id="636be-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="636be-125">Внутренние термины, относящиеся к компании</span><span class="sxs-lookup"><span data-stu-id="636be-125">Company-specific internal terms</span></span>
- <span data-ttu-id="636be-126">Сокращения с определенным значением в компании</span><span class="sxs-lookup"><span data-stu-id="636be-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="636be-127">Вы можете запретить плохие пароли [в облаке](/azure/active-directory/authentication/concept-password-ban-bad) и локальной [AD DS.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)</span><span class="sxs-lookup"><span data-stu-id="636be-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="636be-128">Упрощение входа пользователей</span><span class="sxs-lookup"><span data-stu-id="636be-128">Simplify user sign-in</span></span>

<span data-ttu-id="636be-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) работает с PHS и Pass-Through Authentication (PTA), чтобы позволить пользователям войти в службы, которые используют учетные записи пользователей Azure AD без необходимости вводить пароли, а во многих случаях и их имена пользователей.</span><span class="sxs-lookup"><span data-stu-id="636be-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="636be-130">Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости в дополнительных локальных компонентах, таких как серверы федерации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="636be-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="636be-131">Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="636be-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="636be-132">См. [инструкции по настройке простого единого входа для Azure AD](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="636be-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="636be-133">Упрощение обновлений паролей в AD DS</span><span class="sxs-lookup"><span data-stu-id="636be-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="636be-134">При возврате паролей можно разрешить пользователям сбросить пароли через Azure AD, который затем реплицируется в AD DS.</span><span class="sxs-lookup"><span data-stu-id="636be-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="636be-135">Пользователям не нужно получать доступ к локальной AD DS для обновления паролей.</span><span class="sxs-lookup"><span data-stu-id="636be-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="636be-136">Это важно для роуминга и удаленных пользователей, у которых нет подключения к локальной сети для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="636be-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="636be-137">Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции защиты идентификации Azure AD, например чтобы требовать от пользователей изменять свои локальные пароли при высоком риске компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="636be-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="636be-138">Дополнительные сведения и инструкции по настройке см. в статье [Практическое руководство. Настройка компонента обратной записи паролей](/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="636be-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="636be-139">Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска.</span><span class="sxs-lookup"><span data-stu-id="636be-139">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="636be-140">Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="636be-140">For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="636be-141">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="636be-141">Simplify password resets</span></span>

<span data-ttu-id="636be-142">Сброс пароля самообслуживной службы (SSPR) позволяет пользователям сбросить или разблокировать свои пароли или учетные записи.</span><span class="sxs-lookup"><span data-stu-id="636be-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="636be-143">Чтобы получать оповещения о неправильном или несанкционированном использовании, можно использовать подробные отчеты, которые позволяют отслеживать доступ пользователей к системе, а также уведомления.</span><span class="sxs-lookup"><span data-stu-id="636be-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="636be-144">Прежде чем [](#pw_writeback) развернуть сброс пароля, необходимо включить возврат паролей.</span><span class="sxs-lookup"><span data-stu-id="636be-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="636be-145">См. [инструкции по развертыванию функции сброса паролей](/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="636be-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>