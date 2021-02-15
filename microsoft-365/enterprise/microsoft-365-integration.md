---
title: Интеграция Microsoft 365 с локальной средой
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
description: В этой статье вы узнаете, как интегрировать Microsoft 365 с существующими службами каталогов и локальной средой.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384862"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="3eb2a-103">Интеграция Microsoft 365 с локальной средой</span><span class="sxs-lookup"><span data-stu-id="3eb2a-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="3eb2a-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="3eb2a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3eb2a-105">Microsoft 365 можно интегрировать с существующими доменными службами Active Directory (AD DS) и с локальной установкой Exchange Server, Skype для бизнеса Server 2015 или SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="3eb2a-106">При интеграции AD DS можно синхронизировать учетные записи пользователей для обеих сред и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="3eb2a-107">Вы также можете добавить синхронизацию паролей с помощью PHS или единого входа, чтобы пользователи могли входить в обе среды с помощью своих учетных данных в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="3eb2a-108">При интеграции с серверными продуктами локальной среды создается гибридная среда.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="3eb2a-109">Гибридная среда может помочь при переносе пользователей или сведений в Microsoft 365, а также по-прежнему иметь некоторых пользователей или некоторые сведения в локальной среде и в облаке.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="3eb2a-110">Дополнительные сведения о гибридных средах см. [в гибридном облаке.](../solutions/cloud-architecture-models.md#hybrid)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="3eb2a-111">Вы также можете использовать консультантов Azure Active Directory (Azure AD) для настройки руководства по настройке в Центре администрирования Microsoft 365 (необходимо вошел в Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="3eb2a-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="3eb2a-112">Руководство по настройке Azure AD</span><span class="sxs-lookup"><span data-stu-id="3eb2a-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="3eb2a-113">Синхронизация пользователей из каталога организации</span><span class="sxs-lookup"><span data-stu-id="3eb2a-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="3eb2a-114">Помощник по развертыванию служб федерации Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="3eb2a-115">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="3eb2a-115">Before you begin</span></span>

<span data-ttu-id="3eb2a-116">Перед интеграцией Microsoft 365 и локальной среды необходимо также спланировать сеть [и настроить производительность.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="3eb2a-117">Кроме того, вам необходимо ознакомиться с доступными [моделями удостоверений.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="3eb2a-118">Список средств, которые можно использовать для управления учетной записью пользователя Microsoft [365,](manage-microsoft-365-accounts.md) см. в управлении учетной записью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="3eb2a-119">Интеграция Microsoft 365 с AD DS</span><span class="sxs-lookup"><span data-stu-id="3eb2a-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="3eb2a-120">Если у вас уже есть учетные записи пользователей в AD DS, вы не хотите повторно создавать все эти учетные записи в Microsoft 365 и риск возникновения различий или ошибок между средами.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="3eb2a-121">Синхронизация каталогов позволяет зеркально отражать эти учетные записи между локальной и сетевой средами.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="3eb2a-122">При синхронизации каталогов пользователям не нужно запоминать новые сведения для каждой среды, и вам не нужно создавать или обновлять учетные записи дважды.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="3eb2a-123">Вам потребуется подготовить [свой локальной](prepare-for-directory-synchronization.md) каталог для синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Синхронизация каталогов для синхронизации локальной и сетевой учетных записей пользователей](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="3eb2a-125">Если вы хотите, чтобы пользователи могли входить в Microsoft 365 с помощью своих учетных данных в локальной сети, можно также настроить службу SSO.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="3eb2a-126">С помощью SSO Microsoft 365 настроен на доверие локальной среде для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![При едином входе одна и та же учетная запись доступна как в локальной, так и в сетевой средах.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="3eb2a-128">Синхронизация каталогов с синхронизацией или без синхронизации с паролем или сквозной проверкой подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="3eb2a-129">Пользователь входит в свою локальной среду с помощью своей учетной записи пользователя (домен\имя пользователя).</span><span class="sxs-lookup"><span data-stu-id="3eb2a-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="3eb2a-130">При входе в Microsoft 365 им необходимо снова войти с помощью своей работы или учебной учетной записи (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="3eb2a-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="3eb2a-131">Имя пользователя одинаково в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-131">The user name is the same in both environments.</span></span> <span data-ttu-id="3eb2a-132">При добавлении PHS или PTA пользователь имеет один и тот же пароль для обеих сред, но при входе в Microsoft 365 придется снова вводить эти учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="3eb2a-133">Синхронизация каталогов с помощью PHS — это наиболее часто используемая синхронизация каталогов.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="3eb2a-134">Чтобы настроить синхронизацию службы каталогов, используйте Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="3eb2a-135">Инструкции см. в настройках синхронизации службы каталогов [для Microsoft 365](set-up-directory-synchronization.md) и [Azure AD Connect с помощью экспресс-параметров.](https://go.microsoft.com/fwlink/p/?LinkId=698537)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="3eb2a-136">Узнайте больше о [подготовке к синхронизации службы каталогов с Microsoft 365.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="3eb2a-137">Синхронизация каталогов с SSO</span><span class="sxs-lookup"><span data-stu-id="3eb2a-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="3eb2a-138">Пользователь входит в свою локальной среду с помощью своей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="3eb2a-139">Когда пользователь входит в Microsoft 365, он либо входит в систему автоматически, либо использует те же учетные данные, что и для локальной среды (домен\имя пользователя).</span><span class="sxs-lookup"><span data-stu-id="3eb2a-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="3eb2a-140">Чтобы настроить службу SSO, также используйте Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3eb2a-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="3eb2a-141">Инструкции см. в [настраиваемой установке Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkID=698430)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="3eb2a-142">Дополнительные сведения см. в [документе "Единый вход".](https://go.microsoft.com/fwlink/p/?LinkId=698604)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="3eb2a-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="3eb2a-143">Azure AD Connect</span></span>

<span data-ttu-id="3eb2a-144">Azure AD Connect заменяет более старые версии средств интеграции удостоверений, таких как DirSync и Azure AD Sync. Если вы хотите обновить синхронизацию Azure Active Directory с Azure AD Connect, см. [инструкции по обновлению.](https://go.microsoft.com/fwlink/p/?LinkId=733240)</span><span class="sxs-lookup"><span data-stu-id="3eb2a-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="3eb2a-145">См. также</span><span class="sxs-lookup"><span data-stu-id="3eb2a-145">See also</span></span>

[<span data-ttu-id="3eb2a-146">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="3eb2a-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
