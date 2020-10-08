---
title: Интеграция Microsoft 365 с локальными средами
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
description: В этой статье рассказывается о том, как интегрировать Microsoft 365 с существующими службами каталогов и локальными средами.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384862"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="13933-103">Интеграция Microsoft 365 с локальными средами</span><span class="sxs-lookup"><span data-stu-id="13933-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="13933-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="13933-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="13933-105">Вы можете интегрировать Microsoft 365 с существующими локальными доменными службами Active Directory (AD DS) и локальными установками Exchange Server, Skype для бизнеса Server 2015 или SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="13933-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="13933-106">При интеграции доменных служб Active Directory можно синхронизировать и управлять учетными записями пользователей в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="13933-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="13933-107">Вы также можете добавить синхронизацию хэша паролей (ФС) или единый вход (SSO), чтобы пользователи могли входить в обе среды с помощью локальных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="13933-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="13933-108">При интеграции с локальными серверными продуктами вы создаете гибридную среду.</span><span class="sxs-lookup"><span data-stu-id="13933-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="13933-109">Гибридная среда может помочь при переносе пользователей или информации в Microsoft 365, а также при наличии некоторых пользователей или локальных данных в облаке.</span><span class="sxs-lookup"><span data-stu-id="13933-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="13933-110">Более подробную информацию о гибридных средах можно узнать в разделе [Гибридное облако](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="13933-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="13933-111">Вы также можете использовать советникы Azure Active Directory (Azure AD) для настраиваемых руководств по настройке в центре администрирования Microsoft 365 (необходимо войти в Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="13933-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="13933-112">Руководство по установке Azure AD</span><span class="sxs-lookup"><span data-stu-id="13933-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="13933-113">Синхронизация пользователей из каталога Организации</span><span class="sxs-lookup"><span data-stu-id="13933-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="13933-114">Помощник по развертыванию служб федерации Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="13933-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="13933-115">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="13933-115">Before you begin</span></span>

<span data-ttu-id="13933-116">Перед интеграцией Microsoft 365 и локальной среды необходимо также выполнить [планирование сети и настройку производительности](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="13933-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="13933-117">Вам также потребуется ознакомиться с доступными [моделями удостоверений](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="13933-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="13933-118">В [статье Manage microsoft 365 Accounts](manage-microsoft-365-accounts.md) представлен список средств, которые можно использовать для управления учетными записями пользователей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13933-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="13933-119">Интеграция Microsoft 365 со службами AD DS</span><span class="sxs-lookup"><span data-stu-id="13933-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="13933-120">Если у вас есть учетные записи пользователей в доменных СЛУЖБах Active Directory, вам не нужно повторно создавать все эти учетные записи в Microsoft 365, а также попытаться отличить их между средами.</span><span class="sxs-lookup"><span data-stu-id="13933-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="13933-121">Синхронизация службы каталогов помогает создать зеркальную копию этих учетных записей между локальной средой и интернет-средой.</span><span class="sxs-lookup"><span data-stu-id="13933-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="13933-122">При синхронизации службы каталогов пользователям не нужно запоминать новые сведения для каждой среды, и вам не нужно дважды создавать или обновлять учетные записи.</span><span class="sxs-lookup"><span data-stu-id="13933-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="13933-123">Необходимо [подготовить локальный каталог](prepare-for-directory-synchronization.md) для синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="13933-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Использование синхронизации службы каталогов для синхронизации локальных и сетевых данных учетных записей пользователей](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="13933-125">Если вы хотите, чтобы пользователи могли входить в Microsoft 365 с использованием локальных учетных данных, вы также можете настроить единый вход.</span><span class="sxs-lookup"><span data-stu-id="13933-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="13933-126">При использовании единого входа Microsoft 365 настроен на доверие локальной среде для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="13933-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![При использовании единого входа одна и та же учетная запись доступна как в локальной среде, так и в сети.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="13933-128">Синхронизация службы каталогов с синхронизацией хэша пароля или сквозной проверкой подлинности или без нее (ПТА)</span><span class="sxs-lookup"><span data-stu-id="13933-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="13933-129">Пользователь входит в локальную среду с помощью учетной записи пользователя (домен \ имя_пользователя).</span><span class="sxs-lookup"><span data-stu-id="13933-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="13933-130">При переходе на Microsoft 365 необходимо повторно войти в систему с помощью рабочей или учебной учетной записи (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="13933-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="13933-131">Имя пользователя одинаково в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="13933-131">The user name is the same in both environments.</span></span> <span data-ttu-id="13933-132">При добавлении ФС или ПТА у пользователя будет один и тот же пароль для обеих сред, но при входе в Microsoft 365 потребуется снова предоставить эти учетные данные.</span><span class="sxs-lookup"><span data-stu-id="13933-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="13933-133">Синхронизация каталогов с ФС — это наиболее часто используемая Синхронизация службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="13933-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="13933-134">Чтобы настроить синхронизацию службы каталогов, используйте Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="13933-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="13933-135">Инструкции приведены в разделе [Настройка синхронизации каталогов для Microsoft 365](set-up-directory-synchronization.md) и [Azure AD Connect с параметрами Express](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="13933-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="13933-136">Узнайте больше о [подготовке синхронизации каталогов к Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="13933-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="13933-137">Синхронизация службы каталогов с помощью единого входа</span><span class="sxs-lookup"><span data-stu-id="13933-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="13933-138">Пользователь входит в локальную среду с помощью своей учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="13933-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="13933-139">При переходе на Microsoft 365 они либо автоматически входят в систему, либо выполняют вход в систему, используя те же учетные данные, что и в локальной среде (домен \ имя_пользователя).</span><span class="sxs-lookup"><span data-stu-id="13933-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="13933-140">Для настройки единого входа вы также можете использовать Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="13933-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="13933-141">Инструкции см в разделе [Выборочная установка Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="13933-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="13933-142">Для получения дополнительных сведений см [единый вход](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="13933-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="13933-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="13933-143">Azure AD Connect</span></span>

<span data-ttu-id="13933-144">Azure AD Connect заменяет более ранние версии средств интеграции удостоверений, таких как DirSync и синхронизация Azure AD. Если вы хотите обновить синхронизацию Azure Active Directory с помощью Azure AD Connect, ознакомьтесь [с инструкциями по обновлению](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="13933-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="13933-145">См. также</span><span class="sxs-lookup"><span data-stu-id="13933-145">See also</span></span>

[<span data-ttu-id="13933-146">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="13933-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
