---
title: Включение управления устройствами с Windows 10, подключенными к домену, в Microsoft 365 для бизнеса
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
- M365-identity-device-management
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
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных к Active Directory устройств с Windows 10 в всего несколько этапов.
ms.openlocfilehash: 7bfe5da8701a17712fa249eac99a22b8d5a1b2d1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471054"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="71f2a-103">Управление устройствами с Windows 10, подключенными к домену, с помощью Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="71f2a-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="71f2a-104">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 Business Premium для защиты устройств Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="71f2a-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="71f2a-105">Чтобы настроить эту защиту, можно внедрить **гибридные подключенные устройства Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="71f2a-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="71f2a-106">Эти устройства присоединяются как к локальной службе Active Directory, так и к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71f2a-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="71f2a-107">В этом видеоролике описаны действия, которые необходимо выполнить для наиболее распространенного сценария, который также содержит подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="71f2a-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="71f2a-108">1. Подготовка к синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="71f2a-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="71f2a-109">Перед синхронизацией пользователей и компьютеров из локального домена Active Directory просмотрите статью подготовка к [синхронизации каталогов в Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="71f2a-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="71f2a-110">В частности:</span><span class="sxs-lookup"><span data-stu-id="71f2a-110">In particular:</span></span>

   - <span data-ttu-id="71f2a-111">Убедитесь, что в каталоге нет дубликатов для следующих атрибутов: **mail**, **proxyAddresses**и **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="71f2a-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="71f2a-112">Эти значения должны быть уникальными и все дубликаты должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="71f2a-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="71f2a-113">Рекомендуется настроить атрибут **userPrincipalName** (UPN) для каждой учетной записи локального пользователя, чтобы она соответствовала основному адресу электронной почты, соответствующему лицензированному пользователю Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71f2a-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="71f2a-114">Например: *Mary.Shelley@contoso.com* , а не *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="71f2a-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="71f2a-115">Если домен Active Directory завершается в немаршрутизируемый суффиксе, например. *Local* или *. LAN*, вместо суффикса, поддерживающего маршрутизацию в Интернете, например *. com* или *. org*, сначала измените суффикс UPN локальных учетных записей пользователей, как описано в статье [Подготовка домена, не поддерживающего маршрутизацию, для синхронизации службы каталогов](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="71f2a-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="71f2a-116">2. Установка и настройка Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="71f2a-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="71f2a-117">Чтобы синхронизировать пользователей, группы и контакты из локальной службы Active Directory с Azure Active Directory, установите Azure Active Directory Connect и настройте синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="71f2a-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="71f2a-118">Чтобы узнать больше, ознакомьтесь со статьей [Настройка синхронизации каталогов для Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) .</span><span class="sxs-lookup"><span data-stu-id="71f2a-118">See [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="71f2a-119">Эти действия одинаковы для Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71f2a-119">The steps are exactly the same for Microsoft 365 for business.</span></span> 

<span data-ttu-id="71f2a-120">При настройке параметров для Azure AD Connect рекомендуется включить **синхронизацию паролей**, **единый вход**и функцию **обратной записи паролей** , которая также поддерживается в Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71f2a-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="71f2a-121">Существует несколько дополнительных действий для обратной записи пароля за пределами флажка в службе Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="71f2a-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="71f2a-122">Дополнительные сведения см. [в статье Настройка обратной записи пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="71f2a-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="71f2a-123">3. Настройка гибридного подключения Azure AD</span><span class="sxs-lookup"><span data-stu-id="71f2a-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="71f2a-124">Прежде чем включить гибридные устройства с Windows 10 для гибридной службы Azure AD, убедитесь, что выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="71f2a-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="71f2a-125">Вы используете последнюю версию Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="71f2a-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="71f2a-126">Azure AD Connect синхронизирует все объекты компьютеров устройств, которые вы хотите объединить в гибридную службу Azure AD.</span><span class="sxs-lookup"><span data-stu-id="71f2a-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="71f2a-127">Если объекты компьютера принадлежат определенным подразделениям (OU), убедитесь, что эти подразделения настроены для синхронизации в Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="71f2a-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="71f2a-128">Чтобы зарегистрировать существующие устройства Windows 10, присоединенные к домену, в качестве гибридного подключения к гибридной службе Azure AD, выполните действия, описанные в [руководстве по настройке гибридного подключения Azure Active Directory для управляемых доменов](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="71f2a-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="71f2a-129">Эта гибридная среда позволяет использовать существующую локальную службу Active Directory на компьютерах с Windows 10 и обеспечить их готовность к облачному подключению.</span><span class="sxs-lookup"><span data-stu-id="71f2a-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="71f2a-130">4. Включение автоматической регистрации для Windows 10</span><span class="sxs-lookup"><span data-stu-id="71f2a-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="71f2a-131">Автоматическая регистрация устройств с Windows 10 для управления мобильными устройствами в Intune приведена в статье [Регистрация устройства Windows 10 автоматически с помощью групповой политики](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span><span class="sxs-lookup"><span data-stu-id="71f2a-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="71f2a-132">Вы можете настроить групповую политику на локальном уровне компьютера или для массовых операций, чтобы создать этот параметр групповой политики на контроллере домена с помощью шаблонов консоли управления групповой политикой и ADMX.</span><span class="sxs-lookup"><span data-stu-id="71f2a-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="71f2a-133">5. Настройка беспрепятственного единого входа</span><span class="sxs-lookup"><span data-stu-id="71f2a-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="71f2a-134">Единый единый вход автоматически подписывает пользователей в облачные ресурсы Microsoft 365 при использовании корпоративных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="71f2a-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="71f2a-135">Просто разверните один из двух параметров групповой политики, описанных в статье [Azure Active Directory, обеспечивающей единый вход: краткое](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)руководство.</span><span class="sxs-lookup"><span data-stu-id="71f2a-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="71f2a-136">Параметр **групповой политики** не разрешает пользователям изменять свои параметры, а параметр **групповой политики** задает значения, но также оставляет настраиваемые пользователи настраиваемыми.</span><span class="sxs-lookup"><span data-stu-id="71f2a-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="71f2a-137">6. Настройка Windows Hello для бизнеса</span><span class="sxs-lookup"><span data-stu-id="71f2a-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="71f2a-138">Windows Hello для бизнеса заменяет пароли на строгую двухфакторную проверку подлинности (2FA) для входа на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="71f2a-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="71f2a-139">Один фактор является асимметричной, а другой — ПИН-кодом или другим локальным жестом, таким как "отпечаток пальца" или "распознавание лица", если устройство поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="71f2a-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="71f2a-140">Мы рекомендуем заменять пароли на 2FA и Windows Hello для бизнеса, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="71f2a-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="71f2a-141">Чтобы настроить гибридную Windows Hello для бизнеса, изучите [необходимые условия для развертывания гибридных ключей в Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span><span class="sxs-lookup"><span data-stu-id="71f2a-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="71f2a-142">Затем следуйте инструкциям в статье [Настройка параметров доверия для гибридных ключей Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span><span class="sxs-lookup"><span data-stu-id="71f2a-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
