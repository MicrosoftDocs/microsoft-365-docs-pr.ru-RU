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
description: Синхронизация пользователей, контролируемых доменом, с помощью Microsoft 365 для бизнеса.
ms.openlocfilehash: a22e567fa99456b35742fcf40c07193c96c83cf0
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565691"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="c8ed6-103">Синхронизация пользователей домена с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c8ed6-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="c8ed6-104">1. Подготовка к синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="c8ed6-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="c8ed6-105">Перед синхронизацией пользователей и компьютеров из локального домена Active Directory просмотрите статью подготовка к [синхронизации каталогов в Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c8ed6-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="c8ed6-106">В частности:</span><span class="sxs-lookup"><span data-stu-id="c8ed6-106">In particular:</span></span>

   - <span data-ttu-id="c8ed6-107">Убедитесь, что в каталоге нет дубликатов для следующих атрибутов: **mail**, **proxyAddresses**и **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="c8ed6-108">Эти значения должны быть уникальными и все дубликаты должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="c8ed6-109">Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы она соответствовала основному адресу электронной почты, соответствующему лицензированному пользователю Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="c8ed6-110">Например: *Mary.Shelley@contoso.com* , а не *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="c8ed6-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="c8ed6-111">Если домен Active Directory завершается в немаршрутизируемый суффиксе, например. *Local* или *. LAN*, вместо суффикса, поддерживающего маршрутизацию в Интернете, например *. com* или *. org*, сначала измените суффикс UPN локальных учетных записей пользователей, как описано в статье [Подготовка домена, не поддерживающего маршрутизацию, для синхронизации службы каталогов](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c8ed6-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="c8ed6-112">В разделе **Run IdFix** (4), приведенном ниже, также будет обеспечена готовность локальной службы Active Directory к синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="c8ed6-113">2. Установка и настройка Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c8ed6-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="c8ed6-114">Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, установите Azure Active Directory Connect и настройте синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="c8ed6-115">В центре администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> выберите **Настройка** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="c8ed6-116">В разделе **Вход и безопасность**выберите пункт **Просмотр** в разделе **синхронизация пользователей из каталога вашей организации**.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="c8ed6-117">На странице **синхронизация пользователей из каталога вашей организации** нажмите кнопку **Начало работы**.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="c8ed6-118">На первом шаге запустите средство IdFix, чтобы подготовиться к синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="c8ed6-119">Следуйте указаниям мастера, чтобы скачать Azure AD Connect и использовать его для синхронизации пользователей с управлением домена с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="c8ed6-120">Чтобы узнать больше, ознакомьтесь со статьей [Настройка синхронизации каталогов для Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) .</span><span class="sxs-lookup"><span data-stu-id="c8ed6-120">See [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="c8ed6-121">При настройке параметров для Azure AD Connect рекомендуется включить **синхронизацию паролей**, **единый вход**и функцию **обратной записи паролей** , которая также поддерживается в Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="c8ed6-122">Существует несколько дополнительных действий для обратной записи пароля за пределами флажка в службе Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="c8ed6-123">Дополнительные сведения см. [в статье Настройка обратной записи пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="c8ed6-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="c8ed6-124">Если вы хотите управлять устройствами с Windows 10 с присоединением к домену, обратитесь к разделу [Включение управления подключенными к домену устройств с Windows 10 для управления с помощью Microsoft 365 Business Premium](manage-windows-devices.md) , чтобы настроить гибридное соединение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 