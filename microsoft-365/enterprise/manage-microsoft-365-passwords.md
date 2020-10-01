---
title: Управление паролями учетных записей пользователей Microsoft 365
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
description: Узнайте, как управлять паролями учетных записей пользователей Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328541"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="5cce2-103">Управление паролями учетных записей пользователей Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cce2-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="5cce2-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5cce2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5cce2-105">В зависимости от конфигурации удостоверения можно управлять паролями учетных записей пользователей Microsoft 365 несколькими различными способами.</span><span class="sxs-lookup"><span data-stu-id="5cce2-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="5cce2-106">Вы можете управлять учетными записями пользователей в [центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), в доменных службах Active Directory (AD DS) или в центре администрирования Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5cce2-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="5cce2-107">Планирование того, где и как будут управляться пароли учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="5cce2-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="5cce2-108">Здесь и как можно управлять учетными записями пользователей зависит от модели удостоверений, которую вы хотите использовать для вашей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5cce2-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="5cce2-109">Две модели являются только облачными и гибридными.</span><span class="sxs-lookup"><span data-stu-id="5cce2-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="5cce2-110">Только облако</span><span class="sxs-lookup"><span data-stu-id="5cce2-110">Cloud-only</span></span>

<span data-ttu-id="5cce2-111">Управление паролями учетных записей пользователей в:</span><span class="sxs-lookup"><span data-stu-id="5cce2-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="5cce2-112">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cce2-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- <span data-ttu-id="5cce2-113">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="5cce2-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="5cce2-114">Гибридная среда</span><span class="sxs-lookup"><span data-stu-id="5cce2-114">Hybrid</span></span>

<span data-ttu-id="5cce2-115">При использовании гибридного удостоверения пароли хранятся в доменных СЛУЖБах Active Directory, поэтому для управления паролями учетных записей пользователей необходимо использовать локальные средства AD DS.</span><span class="sxs-lookup"><span data-stu-id="5cce2-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="5cce2-116">Даже при использовании синхронизации со хешированием паролей (ФС), в которой Azure AD сохраняет хешированную версию уже хешированной версии в AD DS, пользователи должны управлять своими паролями в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5cce2-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="5cce2-117">С помощью [обратной записи паролей](#pw_writeback)пользователи могут изменять свои пароли AD DS с помощью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5cce2-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="5cce2-118">Запрет слабых паролей</span><span class="sxs-lookup"><span data-stu-id="5cce2-118">Prevent bad passwords</span></span>

<span data-ttu-id="5cce2-119">Все ваши пользователи должны применять [Руководство по паролям корпорации Майкрософт](https://www.microsoft.com/research/publication/password-guidance) для создания своих паролей учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="5cce2-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="5cce2-120">Чтобы запретить пользователям создавать легко подбираемые пароли, применяйте службу защиты паролей Azure AD, в которой используется как глобальный список запрещенных паролей, так и необязательный настраиваемый список запрещенных паролей, указываемый вами.</span><span class="sxs-lookup"><span data-stu-id="5cce2-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="5cce2-121">Например, вы можете указать следующие термины, относящиеся к вашей организации:</span><span class="sxs-lookup"><span data-stu-id="5cce2-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="5cce2-122">Фирменные названия</span><span class="sxs-lookup"><span data-stu-id="5cce2-122">Brand names</span></span>
- <span data-ttu-id="5cce2-123">Названия продуктов</span><span class="sxs-lookup"><span data-stu-id="5cce2-123">Product names</span></span>
- <span data-ttu-id="5cce2-124">Расположения (например, штаб-квартира компании)</span><span class="sxs-lookup"><span data-stu-id="5cce2-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="5cce2-125">Внутренние термины, относящиеся к компании</span><span class="sxs-lookup"><span data-stu-id="5cce2-125">Company-specific internal terms</span></span>
- <span data-ttu-id="5cce2-126">Сокращения с определенным значением в компании</span><span class="sxs-lookup"><span data-stu-id="5cce2-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="5cce2-127">Вы можете запретить неправильные пароли [в облаке](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) и для [локальных доменных служб Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="5cce2-127">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="5cce2-128">Упрощение входа пользователей</span><span class="sxs-lookup"><span data-stu-id="5cce2-128">Simplify user sign-in</span></span>

<span data-ttu-id="5cce2-129">Единый вход в Azure AD (единый вход Azure AD) работает с ФС и сквозной проверкой подлинности (ПТА), чтобы позволить пользователям входить в службы, использующие учетные записи пользователей Azure AD, не вводя их пароли, и во многих случаях их имена.</span><span class="sxs-lookup"><span data-stu-id="5cce2-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="5cce2-130">Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости в дополнительных локальных компонентах, таких как серверы федерации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="5cce2-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="5cce2-131">Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="5cce2-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="5cce2-132">См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="5cce2-132">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="5cce2-133">Упрощение обновления паролей для доменных служб Active Directory</span><span class="sxs-lookup"><span data-stu-id="5cce2-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="5cce2-134">С помощью обратной записи паролей можно разрешить пользователям сбрасывать свои пароли через Azure AD, которая затем реплицируется в AD DS.</span><span class="sxs-lookup"><span data-stu-id="5cce2-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="5cce2-135">Пользователям не требуется доступ к локальным доменным СЛУЖБам Active Directory для обновления своих паролей.</span><span class="sxs-lookup"><span data-stu-id="5cce2-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="5cce2-136">Это важно для роуминга и удаленных пользователей, у которых нет подключения к локальной сети для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="5cce2-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="5cce2-137">Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции защиты идентификации Azure AD, например чтобы требовать от пользователей изменять свои локальные пароли при высоком риске компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5cce2-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="5cce2-138">Дополнительные сведения и инструкции по настройке см. в статье [Практическое руководство. Настройка компонента обратной записи паролей](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="5cce2-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="5cce2-139">Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска.</span><span class="sxs-lookup"><span data-stu-id="5cce2-139">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="5cce2-140">Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="5cce2-140">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="5cce2-141">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="5cce2-141">Simplify password resets</span></span>

<span data-ttu-id="5cce2-142">Самостоятельный сброс паролей (SSPR) позволяет пользователям сбрасывать или разблокировать пароли и учетные записи.</span><span class="sxs-lookup"><span data-stu-id="5cce2-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="5cce2-143">Чтобы получать оповещения о неправильном или несанкционированном использовании, можно использовать подробные отчеты, которые позволяют отслеживать доступ пользователей к системе, а также уведомления.</span><span class="sxs-lookup"><span data-stu-id="5cce2-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="5cce2-144">Для развертывания сброса паролей необходимо включить [обратную запись пароля](#pw_writeback) .</span><span class="sxs-lookup"><span data-stu-id="5cce2-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="5cce2-145">См. [инструкции по развертыванию функции сброса паролей](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="5cce2-145">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

