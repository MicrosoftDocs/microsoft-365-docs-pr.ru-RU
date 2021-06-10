---
title: Microsoft 365 интеграции с локальной средой
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: В этой статье узнайте, как интегрировать Microsoft 365 с существующими службами каталогов и локальной средой.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923970"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="86afc-103">Microsoft 365 интеграции с локальной средой</span><span class="sxs-lookup"><span data-stu-id="86afc-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="86afc-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="86afc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="86afc-105">Можно интегрировать Microsoft 365 с существующими локально-доменными службами Active Directory (AD DS) и с локальной установкой Exchange Server, Skype для бизнеса Server 2015 или SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="86afc-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="86afc-106">При интеграции AD DS можно синхронизировать и управлять учетной записью пользователей для обеих сред.</span><span class="sxs-lookup"><span data-stu-id="86afc-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="86afc-107">Вы также можете добавить синхронизацию с hash паролем (PHS) или один вход (SSO), чтобы пользователи могли войти в обе среды с учетными данными на месте.</span><span class="sxs-lookup"><span data-stu-id="86afc-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="86afc-108">При интеграции с локальной серверной продукцией создается гибридная среда.</span><span class="sxs-lookup"><span data-stu-id="86afc-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="86afc-109">Гибридная среда может помочь при переносе пользователей или сведений в Microsoft 365, или вы можете продолжать иметь некоторых пользователей или некоторые сведения на локальной основе, а некоторые в облаке.</span><span class="sxs-lookup"><span data-stu-id="86afc-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="86afc-110">Дополнительные сведения о гибридных средах см. в [гибридном облаке.](../solutions/cloud-architecture-models.md#hybrid)</span><span class="sxs-lookup"><span data-stu-id="86afc-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="86afc-111">Вы также можете использовать Azure Active Directory (Azure AD) для настраиваемых руководств по настройке в центре администрирования Microsoft 365 (вы должны быть подписаны в Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="86afc-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="86afc-112">Руководство по настройке Azure AD</span><span class="sxs-lookup"><span data-stu-id="86afc-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="86afc-113">Синхронизация пользователей из каталога вашей организации</span><span class="sxs-lookup"><span data-stu-id="86afc-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="86afc-114">Советник по развертыванию служб Федерации Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="86afc-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="86afc-115">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="86afc-115">Before you begin</span></span>

<span data-ttu-id="86afc-116">Перед интеграцией Microsoft 365 локальной среды необходимо также сделать планирование сети [и настройку производительности.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="86afc-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="86afc-117">Кроме того, необходимо разобраться в доступных [моделях удостоверений.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="86afc-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="86afc-118">См. [Microsoft 365 учетные записи](manage-microsoft-365-accounts.md) для списка средств, которые можно использовать для управления Microsoft 365 учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="86afc-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="86afc-119">Интеграция Microsoft 365 с AD DS</span><span class="sxs-lookup"><span data-stu-id="86afc-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="86afc-120">Если у вас есть существующие учетные записи пользователей в AD DS, вы не хотите повторно создавать все эти учетные записи в Microsoft 365 и рискуете ввести различия или ошибки между средами.</span><span class="sxs-lookup"><span data-stu-id="86afc-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="86afc-121">Синхронизация каталогов позволяет зеркально отражать эти учетные записи между локальной и интернет-средой.</span><span class="sxs-lookup"><span data-stu-id="86afc-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="86afc-122">При синхронизации каталогов пользователям не нужно запоминать новые сведения для каждой среды, и вам не нужно создавать или обновлять учетные записи дважды.</span><span class="sxs-lookup"><span data-stu-id="86afc-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="86afc-123">Вам потребуется подготовить [локальное каталог](prepare-for-directory-synchronization.md) для синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="86afc-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Синхронизация каталогов используется для синхронизации сведений о учетных записях пользователей на локальной основе и учетных записях пользователей в Интернете.](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="86afc-125">Если вы хотите, чтобы пользователи могли войти в систему Microsoft 365 с учетными данными локального пользователя, можно также настроить SSO.</span><span class="sxs-lookup"><span data-stu-id="86afc-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="86afc-126">С помощью SSO Microsoft 365 настраивается для доверия локальной среде для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="86afc-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![С одним входом одна учетная запись доступна как в локальной, так и в онлайн-среде.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="86afc-128">Синхронизация каталогов с синхронизацией с хашированием или проверкой подлинности с помощью пароля или без него (PTA)</span><span class="sxs-lookup"><span data-stu-id="86afc-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="86afc-129">Пользователь входит в локальное окружение со своей учетной записью пользователя (domain\username).</span><span class="sxs-lookup"><span data-stu-id="86afc-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="86afc-130">Когда они идут в Microsoft 365, они должны снова войти в систему со своей учетной записью работы или школы (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="86afc-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="86afc-131">Имя пользователя одинаково в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="86afc-131">The user name is the same in both environments.</span></span> <span data-ttu-id="86afc-132">При добавлении PHS или PTA у пользователя есть один и тот же пароль для обеих сред, но при входе в систему Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86afc-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="86afc-133">Синхронизация каталогов с PHS является наиболее часто используемой синхронизацией каталогов.</span><span class="sxs-lookup"><span data-stu-id="86afc-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="86afc-134">Чтобы настроить синхронизацию каталогов, используйте Azure AD Подключение.</span><span class="sxs-lookup"><span data-stu-id="86afc-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="86afc-135">Инструкции см. [в](set-up-directory-synchronization.md) инструкции Настройка синхронизации каталогов для Microsoft 365 [и Azure AD Подключение с экспресс-настройками.](/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="86afc-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="86afc-136">Дополнительные данные [о подготовке к синхронизации каталогов с Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="86afc-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="86afc-137">Синхронизация каталогов с SSO</span><span class="sxs-lookup"><span data-stu-id="86afc-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="86afc-138">Пользователь входит в локальное окружение со своей учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="86afc-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="86afc-139">При входе в Microsoft 365 они автоматически включались в систему, либо войдут в систему с использованием тех же учетных данных, что и для локальной среды (domain\username).</span><span class="sxs-lookup"><span data-stu-id="86afc-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="86afc-140">Чтобы настроить SSO, вы также используете Azure AD Подключение.</span><span class="sxs-lookup"><span data-stu-id="86afc-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="86afc-141">Инструкции см. в [специальной установке Azure AD Подключение.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="86afc-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="86afc-142">Дополнительные сведения см. [в одном входе.](/azure/active-directory/manage-apps/what-is-single-sign-on)</span><span class="sxs-lookup"><span data-stu-id="86afc-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="86afc-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="86afc-143">Azure AD Connect</span></span>

<span data-ttu-id="86afc-144">Azure AD Подключение старые версии средств интеграции удостоверений, таких как DirSync и Azure AD Sync. Если требуется обновить Azure Active Directory синхронизации с Azure AD Подключение, см. [инструкции по обновлению.](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)</span><span class="sxs-lookup"><span data-stu-id="86afc-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="86afc-145">См. также</span><span class="sxs-lookup"><span data-stu-id="86afc-145">See also</span></span>

[<span data-ttu-id="86afc-146">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="86afc-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)