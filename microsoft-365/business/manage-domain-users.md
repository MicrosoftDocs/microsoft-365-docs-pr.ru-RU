---
title: Синхронизация пользователей домена с Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Синхронизировать пользователей, управляемых доменом, с Microsoft 365 для бизнеса.
ms.openlocfilehash: 1c939dec7229f02991b15f08c48f184efecaddb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913261"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="3b6f6-103">Синхронизация пользователей домена с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b6f6-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="3b6f6-104">1. Подготовка к синхронизации каталогов</span><span class="sxs-lookup"><span data-stu-id="3b6f6-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="3b6f6-105">Прежде чем синхронизировать пользователей и компьютеры с локального домена Active Directory, просмотрите подготовку к синхронизации каталогов с [Microsoft 365.](../enterprise/prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="3b6f6-106">В частности:</span><span class="sxs-lookup"><span data-stu-id="3b6f6-106">In particular:</span></span>

   - <span data-ttu-id="3b6f6-107">Убедитесь, что в каталоге не существует дубликатов для следующих атрибутов: **почты,** **proxyAddresses** и **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="3b6f6-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="3b6f6-108">Эти значения должны быть уникальными, и любые дубликаты должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="3b6f6-109">Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы соответствовать основному адресу электронной почты, соответствующему лицензированным пользователю Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="3b6f6-110">Например: *mary.shelley@contoso.com,* *а не mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="3b6f6-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="3b6f6-111">Если домен Active Directory заканчивается суффиксом без маршрутизации, например *.local* или *.lan,* вместо суффикса для маршрутизации интернета, например *.com* или *.org,* сначала настройтесь на суффикс учетных записей локальных пользователей, как описано в "Подготовка ненаправимого домена для синхронизации каталогов". [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="3b6f6-112">Запуск **IdFix** в шаге 4 (4) ниже, также убедитесь, что локальное Active Directory готово к синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="3b6f6-113">2. Установка и настройка Подключения Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b6f6-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="3b6f6-114">Чтобы синхронизировать пользователей, группы и контакты из локального Active Directory в Azure Active Directory, установите Azure Active Directory Connect и установите синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="3b6f6-115">В центре [администрирования](https://go.microsoft.com/fwlink/p/?linkid=2024339)выберите **Установку** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="3b6f6-116">В **соответствии с входом и безопасностью** выберите **Просмотр**  под синхронизацией пользователей **из каталога вашей организации**.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="3b6f6-117">На странице Sync пользователи со страницы **каталога** вашей организации выберите **Начало работы.**</span><span class="sxs-lookup"><span data-stu-id="3b6f6-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="3b6f6-118">На первом этапе запустите средство IdFix для подготовки к синхронизации Каталог.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="3b6f6-119">Выполните действия мастера, чтобы скачать Azure AD Connect и использовать его для синхронизации пользователей, управляемых доменом, с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="3b6f6-120">Дополнительные данные см. в дополнительных подробной информации о синхронизации каталогов [для Microsoft 365.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="3b6f6-121">При настройке параметров Azure AD Connect рекомендуется включить синхронизацию паролей, бесшовную одновокую запись и функцию записи паролей, которая также поддерживается в Microsoft 365 для бизнеса. </span><span class="sxs-lookup"><span data-stu-id="3b6f6-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="3b6f6-122">Есть несколько дополнительных действий для списания пароля за пределами контрольного окна в Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="3b6f6-123">Дополнительные сведения см. в [статью How-to: настройка записи пароля.](/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="3b6f6-124">Если вы также хотите управлять устройствами Windows 10, присоединив к домену, см. в статью Включить устройства Windows 10, которые будут управляться Microsoft [365 Business Premium,](manage-windows-devices.md) чтобы создать гибридную службу Azure AD Join.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>