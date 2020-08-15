---
title: Интеграция Microsoft 365 с локальными средами
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693520"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="e265c-103">Интеграция Microsoft 365 с локальными средами</span><span class="sxs-lookup"><span data-stu-id="e265c-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="e265c-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e265c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e265c-105">Вы можете интегрировать Microsoft 365 с существующими службами каталогов и с локальной установкой Exchange Server, Skype для бизнеса Server 2015 или SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="e265c-105">You can integrate Microsoft 365 with your existing directory services and with an on-premises installation of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="e265c-106">При интеграции со службами каталогов можно синхронизировать и управлять учетными записями пользователей в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="e265c-106">When you integrate with directory services, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="e265c-107">Вы также можете добавить синхронизацию хэша паролей или единый вход (SSO), чтобы пользователи могли входить в обе среды с их локальными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="e265c-107">You can also add password hash synchronization or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="e265c-108">При интеграции с локальными серверными продуктами вы создаете гибридную среду.</span><span class="sxs-lookup"><span data-stu-id="e265c-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="e265c-109">Гибридная среда может помочь при переносе пользователей или информации в Microsoft 365, а также при наличии некоторых пользователей или локальных данных в облаке.</span><span class="sxs-lookup"><span data-stu-id="e265c-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="e265c-110">Более подробную информацию о гибридных средах можно найти в статье [Обзор гибридного облака](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="e265c-110">For more information about hybrid environments, see [Hybrid cloud overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span></span>

<span data-ttu-id="e265c-111">Вы также можете использовать советникы Azure Active Directory (Azure AD) для настраиваемых руководств по настройке (необходимо войти в Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="e265c-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="e265c-112">Синхронизация пользователей из каталога Организации</span><span class="sxs-lookup"><span data-stu-id="e265c-112">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="e265c-113">Помощник по развертыванию AD FS</span><span class="sxs-lookup"><span data-stu-id="e265c-113">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
- [<span data-ttu-id="e265c-114">Руководство по установке Azure AD</span><span class="sxs-lookup"><span data-stu-id="e265c-114">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="e265c-115">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e265c-115">Before you begin</span></span>

<span data-ttu-id="e265c-116">Перед интеграцией Microsoft 365 и локальной среды также необходимо принять участие в [планировании сети и настройке производительности](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="e265c-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to attend to [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="e265c-117">Вам также потребуется ознакомиться с доступными [моделями удостоверений](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="e265c-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="e265c-118">Узнайте, [где можно управлять учетными записями microsoft 365](manage-microsoft-365-accounts.md) , чтобы получить список средств, которые можно использовать для управления пользователями и учетными записями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e265c-118">See [where to manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 users and accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-directory-services"></a><span data-ttu-id="e265c-119">Интеграция Microsoft 365 со службами каталогов</span><span class="sxs-lookup"><span data-stu-id="e265c-119">Integrate Microsoft 365 with directory services</span></span>
<span data-ttu-id="e265c-120">Если у вас есть учетные записи пользователей в локальном каталоге, вы не хотите повторно создавать все эти учетные записи в Microsoft 365, а также попытаться попадать в нее различия или ошибки.</span><span class="sxs-lookup"><span data-stu-id="e265c-120">If you have existing user accounts in an on-premises directory, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="e265c-121">Синхронизация службы каталогов помогает создать зеркальную копию этих учетных записей между локальной средой и Интернетом.</span><span class="sxs-lookup"><span data-stu-id="e265c-121">Directory synchronization helps you mirror those accounts between your online and on-premises environments.</span></span> <span data-ttu-id="e265c-122">При синхронизации службы каталогов пользователям не нужно запоминать новые сведения для каждой среды, и вам не нужно дважды создавать или обновлять учетные записи.</span><span class="sxs-lookup"><span data-stu-id="e265c-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="e265c-123">Необходимо [подготовить локальный каталог](prepare-for-directory-synchronization.md) для синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="e265c-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Использование синхронизации службы каталогов для синхронизации локальных и сетевых данных учетных записей пользователей](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
<span data-ttu-id="e265c-125">Если вы хотите, чтобы пользователи могли входить в Microsoft 365 с использованием локальных учетных данных, вы также можете настроить единый вход.</span><span class="sxs-lookup"><span data-stu-id="e265c-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="e265c-126">При использовании единого входа Microsoft 365 настроен на доверие локальной среде для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="e265c-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![При использовании единого входа одна и та же учетная запись доступна как в локальной среде, так и в сети.](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
<span data-ttu-id="e265c-128">Различные методы управления учетными записями пользователей предоставляют различные возможности для пользователей, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e265c-128">Different user account management techniques provide different experiences for your users, as shown in the following table.</span></span>
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a><span data-ttu-id="e265c-129">Синхронизация службы каталогов с или без синхронизации хэша паролей или сквозной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e265c-129">Directory synchronization with or without password hash synchronization or pass-through authentication</span></span>

<span data-ttu-id="e265c-130">Пользователь входит в локальную среду с помощью учетной записи пользователя (домен \ имя_пользователя).</span><span class="sxs-lookup"><span data-stu-id="e265c-130">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="e265c-131">При переходе на Microsoft 365 необходимо повторно войти в систему с помощью рабочей или учебной учетной записи (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="e265c-131">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="e265c-132">Имя пользователя одинаково в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="e265c-132">The user name is the same in both environments.</span></span> <span data-ttu-id="e265c-133">При добавлении синхронизации хэша пароля или сквозной проверки подлинности у пользователя будет один и тот же пароль для обеих сред, но при входе в Microsoft 365 потребуется предоставить эти учетные данные повторно.</span><span class="sxs-lookup"><span data-stu-id="e265c-133">When you add password hash sync or pass-through authentication, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="e265c-134">Синхронизация службы каталогов с синхронизацией хэша паролей является наиболее часто используемым сценарием синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="e265c-134">Directory synchronization with password hash sync is the most commonly used directory sync scenario.</span></span>

<span data-ttu-id="e265c-135">Чтобы настроить синхронизацию службы каталогов, используйте Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="e265c-135">To set up directory synchronization, use Azure Active Directory Connect.</span></span> <span data-ttu-id="e265c-136">Для получения инструкций прочитайте статью [Настройка синхронизации каталогов для Microsoft 365](set-up-directory-synchronization.md)и [Azure AD Connect с параметрами Express](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="e265c-136">For instructions, read [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md), and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="e265c-137">Узнайте больше о [подготовке синхронизации каталогов к Microsoft 365](prepare-for-directory-synchronization.md) и [интеграции локальной идентификации с Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span><span class="sxs-lookup"><span data-stu-id="e265c-137">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md) and [integrating your on-premises identifies with Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="e265c-138">Синхронизация службы каталогов с помощью единого входа</span><span class="sxs-lookup"><span data-stu-id="e265c-138">Directory synchronization with SSO</span></span>

<span data-ttu-id="e265c-139">Пользователь входит в локальную среду с помощью своей учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e265c-139">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="e265c-140">При переходе на Microsoft 365 они либо автоматически входят в систему, либо выполняют вход в систему, используя те же учетные данные, что и в локальной среде (домен \ имя_пользователя).</span><span class="sxs-lookup"><span data-stu-id="e265c-140">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="e265c-141">Для настройки единого входа вы также можете использовать Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="e265c-141">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="e265c-142">Инструкции по чтению [настраиваемой установки Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="e265c-142">For instructions, read [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="e265c-143">Узнайте больше о [едином входе в приложения в Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="e265c-143">Learn more about [single sign-on to applications in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="e265c-144">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="e265c-144">Azure AD Connect</span></span>

<span data-ttu-id="e265c-145">Azure AD Connect заменяет более ранние версии средств интеграции удостоверений, таких как DirSync и синхронизация Azure AD. Для получения дополнительных сведений Узнайте, [что такое гибридное удостоверение с Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span><span class="sxs-lookup"><span data-stu-id="e265c-145">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. For more information, see [What is hybrid identity with Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span></span> <span data-ttu-id="e265c-146">Если вы хотите обновить синхронизацию Azure Active Directory с помощью Azure AD Connect, ознакомьтесь [с инструкциями по обновлению](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="e265c-146">If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

<span data-ttu-id="e265c-147">Кроме того, вы можете ознакомиться со статьей [развертывание microsoft 365 Directory Synchronization в Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span><span class="sxs-lookup"><span data-stu-id="e265c-147">Also see [Deploy Microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span></span>

## <a name="see-also"></a><span data-ttu-id="e265c-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e265c-148">See also</span></span>

[<span data-ttu-id="e265c-149">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e265c-149">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
