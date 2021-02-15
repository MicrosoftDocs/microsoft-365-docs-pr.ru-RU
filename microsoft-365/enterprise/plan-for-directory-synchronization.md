---
title: Гибридная синхронизация удостоверений и каталогов для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Описывает синхронизацию службы каталогов с Microsoft 365, очисткой доменных служб Active Directory и средством Azure Active Directory Connect.
ms.openlocfilehash: 02b594f9db02df7e855a20dfc65b21ab2dbe91c0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327383"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="1656b-103">Гибридная синхронизация удостоверений и каталогов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1656b-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="1656b-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1656b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1656b-105">В зависимости от бизнес-потребностей и технических требований гибридная модель удостоверений и синхронизация службы каталогов — это наиболее распространенный вариант для корпоративных клиентов, которые принимают Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="1656b-106">Синхронизация службы каталогов позволяет управлять удостоверениями в доменных службах Active Directory (AD DS), а все обновления учетных записей пользователей, групп и контактов синхронизируются с клиентом Azure Active Directory (Azure AD) подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="1656b-107">Когда учетные записи пользователей AD DS синхронизируются в первый раз, им не будет автоматически назначена лицензия Microsoft 365 и они не смогут получить доступ к службам Microsoft 365, таким как электронная почта.</span><span class="sxs-lookup"><span data-stu-id="1656b-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="1656b-108">Сначала необходимо назначить им место использования.</span><span class="sxs-lookup"><span data-stu-id="1656b-108">You must first assign them a usage location.</span></span> <span data-ttu-id="1656b-109">Затем назначьте лицензию этим учетным записям пользователей по отдельности или динамически посредством членства в группах.</span><span class="sxs-lookup"><span data-stu-id="1656b-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="1656b-110">Проверка подлинности для гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="1656b-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="1656b-111">Существует два типа проверки подлинности при использовании гибридной модели удостоверений:</span><span class="sxs-lookup"><span data-stu-id="1656b-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="1656b-112">Управляемая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1656b-112">Managed authentication</span></span>

  <span data-ttu-id="1656b-113">Azure AD обрабатывает процесс проверки подлинности с помощью локально сохраненной версии пароля с использованием hashed или отправляет учетные данные локальному агенту программного обеспечения для проверки подлинности локальной службой AD DS.</span><span class="sxs-lookup"><span data-stu-id="1656b-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="1656b-114">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="1656b-114">Federated authentication</span></span>

  <span data-ttu-id="1656b-115">Azure AD перенаправляет клиентский компьютер, запрашивающий проверку подлинности, другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="1656b-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="1656b-116">Управляемая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1656b-116">Managed authentication</span></span>

<span data-ttu-id="1656b-117">Существует два типа управляемой проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="1656b-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="1656b-118">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="1656b-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="1656b-119">Проверка подлинности выполняется с помощью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1656b-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="1656b-120">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="1656b-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="1656b-121">Проверка подлинности выполняется с помощью доменных служб Aсtive Directory в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1656b-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="1656b-122">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="1656b-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="1656b-123">С помощью PHS вы синхронизируете учетные записи пользователей AD DS с Microsoft 365 и управляете пользователями локально.</span><span class="sxs-lookup"><span data-stu-id="1656b-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="1656b-124">Хеши паролей пользователей синхронизируются из AD DS в Azure AD, чтобы у пользователей был одинаковый пароль как в локальной, так и в облаке.</span><span class="sxs-lookup"><span data-stu-id="1656b-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="1656b-125">Это самый простой способ включить проверку подлинности для удостоверений AD DS в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1656b-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Синхронизация хэша паролей (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="1656b-127">При изменении или сбросе паролей в локальной службе новые хеши паролей синхронизируются с Azure AD, чтобы пользователи всегда могли использовать один и тот же пароль для облачных и локального ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1656b-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="1656b-128">Пароли пользователей никогда не отправляются в Azure AD и не хранятся в Azure AD в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="1656b-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="1656b-129">Некоторые дополнительные функции Azure AD, такие как защита идентификации, требуют PHS независимо от выбранного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1656b-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="1656b-130">См. выбор правильного метода [проверки подлинности,](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="1656b-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="1656b-131">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="1656b-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="1656b-132">PTA обеспечивает простую проверку пароля для служб проверки подлинности Azure AD с помощью агента программного обеспечения, запущенного на одном или более локальном сервере для проверки пользователей непосредственно с помощью AD DS.</span><span class="sxs-lookup"><span data-stu-id="1656b-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="1656b-133">С помощью PTA вы синхронизируете учетные записи пользователей AD DS с Microsoft 365 и управляете пользователями локально.</span><span class="sxs-lookup"><span data-stu-id="1656b-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Сквозная проверка подлинности (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="1656b-135">PTA позволяет пользователям вводить как локальное, так и microsoft 365-ресурсы и приложения с помощью локальной учетной записи и пароля.</span><span class="sxs-lookup"><span data-stu-id="1656b-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="1656b-136">Эта конфигурация проверяет пароли пользователей непосредственно в локальной службе AD DS без хранения хеш-кодов паролей в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1656b-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="1656b-137">PTA также для организаций с требованием безопасности для немедленного принудительного применения локального состояния учетных записей пользователей, политик паролей и часов для работы с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="1656b-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="1656b-138">См. выбор правильного метода [проверки подлинности,](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="1656b-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="1656b-139">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="1656b-139">Federated authentication</span></span>

<span data-ttu-id="1656b-140">Федераированная проверка подлинности в основном предназначена для крупных корпоративных организаций с более сложными требованиями к проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="1656b-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="1656b-141">Удостоверения AD DS синхронизируются с Microsoft 365, а учетные записи пользователей управляются локально.</span><span class="sxs-lookup"><span data-stu-id="1656b-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="1656b-142">При использовании федераированной проверки подлинности пользователи имеют одинаковый пароль как в локальной, так и в облаке, и им не нужно повторно входить в учетную запись, чтобы использовать Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="1656b-143">Федеративная проверка подлинности может поддерживать дополнительные требования к проверке подлинности, такие как проверка подлинности на основе смарт-карт или сторонней многофакторной проверки подлинности, и обычно требуется, если для организаций требование проверки подлинности не поддерживается в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1656b-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="1656b-144">См. выбор правильного метода [проверки подлинности,](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="1656b-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="1656b-145">Сторонние поставщики проверки подлинности и удостоверений</span><span class="sxs-lookup"><span data-stu-id="1656b-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="1656b-146">Объекты локального каталога можно синхронизировать с Microsoft 365, а доступом к облачным ресурсам в основном управляет сторонний поставщик удостоверений (IdP).</span><span class="sxs-lookup"><span data-stu-id="1656b-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="1656b-147">Если ваша организация использует стороне решение федерации, вы можете настроить вход с помощью этого решения для Microsoft 365 при условии, что стороне решение федерации совместимо с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1656b-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="1656b-148">Подробнее [см. в списке совместимости федерации Azure AD.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility)</span><span class="sxs-lookup"><span data-stu-id="1656b-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="1656b-149">Подготовка AD DS</span><span class="sxs-lookup"><span data-stu-id="1656b-149">AD DS Preparation</span></span>

<span data-ttu-id="1656b-150">Чтобы обеспечить бесперебойный переход на Microsoft 365 с помощью синхронизации, необходимо подготовить лес AD DS перед началом развертывания синхронизации службы каталогов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="1656b-151">Подготовка каталога должна быть сфокусирована на следующих задачах:</span><span class="sxs-lookup"><span data-stu-id="1656b-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="1656b-152">Удалите **повторяющиеся** атрибуты **proxyAddress и userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="1656b-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="1656b-153">Обновим пустые и недопустимые **атрибуты userPrincipalName** допустимыми **атрибутами userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="1656b-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="1656b-154">Удалите недопустимые и сомнительные символы в атрибутах **givenName**, surname ( **sn),** **sAMAccountName,** **displayName**, **mail**, **proxyAddresses,** **mailNickname** и **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="1656b-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="1656b-155">Подробные сведения о подготовке атрибутов см. в списке атрибутов, синхронизированных средством [синхронизации Azure Active Directory.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="1656b-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1656b-156">Это те же атрибуты, которые синхронизирует Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1656b-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="1656b-157">Вопросы развертывания с несколькими лесами</span><span class="sxs-lookup"><span data-stu-id="1656b-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="1656b-158">Для нескольких лесов и параметров SSO используйте настраиваемую установку [Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkId=698430)</span><span class="sxs-lookup"><span data-stu-id="1656b-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="1656b-159">Если в организации имеется несколько лесов для проверки подлинности (лесов для проверки подлинности), настоятельно рекомендуется следующее:</span><span class="sxs-lookup"><span data-stu-id="1656b-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="1656b-160">**Рассмотрите возможность объединения лесов.**</span><span class="sxs-lookup"><span data-stu-id="1656b-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="1656b-161">Как правило, для обслуживания нескольких лесов требуются дополнительные дополнительные расходы.</span><span class="sxs-lookup"><span data-stu-id="1656b-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="1656b-162">Если в организации нет ограничений безопасности, которые определяют необходимость отдельных лесов, рассмотрите возможность упрощения локальной среды.</span><span class="sxs-lookup"><span data-stu-id="1656b-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="1656b-163">**Используйте только в основном лесу для логотипа.**</span><span class="sxs-lookup"><span data-stu-id="1656b-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="1656b-164">Рассмотрите возможность развертывания Microsoft 365 только в основном лесу для первого развертывания Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="1656b-165">Если вам не удается консолидировать развертывание AD DS с несколькими лесами или вы используете другие службы каталогов для управления удостоверениями, вы можете синхронизировать их с помощью Майкрософт или партнера.</span><span class="sxs-lookup"><span data-stu-id="1656b-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="1656b-166">Дополнительные [сведения см. в "Topologies for Azure AD Connect".](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)</span><span class="sxs-lookup"><span data-stu-id="1656b-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="1656b-167">Функции, зависящие от синхронизации каталогов</span><span class="sxs-lookup"><span data-stu-id="1656b-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="1656b-168">Синхронизация службы каталогов необходима для следующих функций:</span><span class="sxs-lookup"><span data-stu-id="1656b-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="1656b-169">Единый единый Sign-On Azure AD</span><span class="sxs-lookup"><span data-stu-id="1656b-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="1656b-170">Сосуществование Skype</span><span class="sxs-lookup"><span data-stu-id="1656b-170">Skype coexistence</span></span>
- <span data-ttu-id="1656b-171">Гибридное развертывание Exchange, в том числе:</span><span class="sxs-lookup"><span data-stu-id="1656b-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="1656b-172">Полный общий глобальный список адресов (GAL) между локальной средой Exchange и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="1656b-173">синхронизацию данных глобального списка адресов из разных почтовых систем;</span><span class="sxs-lookup"><span data-stu-id="1656b-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="1656b-174">Возможность добавлять и удалять пользователей из служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="1656b-175">Для этого необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="1656b-175">This requires the following:</span></span>
  - <span data-ttu-id="1656b-176">Двунастройную синхронизацию необходимо настроить во время настройки синхронизации каталогов.</span><span class="sxs-lookup"><span data-stu-id="1656b-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="1656b-177">По умолчанию средства синхронизации каталогов записывают сведения о каталоге только в облако.</span><span class="sxs-lookup"><span data-stu-id="1656b-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="1656b-178">При настройке двухнастройной синхронизации включается функция обратного копирования, чтобы скопировать ограниченное количество атрибутов объекта из облака, а затем записать их обратно в локальные AD DS.</span><span class="sxs-lookup"><span data-stu-id="1656b-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="1656b-179">Обратное написание также называется гибридным режимом Exchange.</span><span class="sxs-lookup"><span data-stu-id="1656b-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="1656b-180">Локальное гибридное развертывание Exchange</span><span class="sxs-lookup"><span data-stu-id="1656b-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="1656b-181">Возможность перемещения некоторых почтовых ящиков пользователей в Microsoft 365, сохраняя другие почтовые ящики пользователей локально.</span><span class="sxs-lookup"><span data-stu-id="1656b-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="1656b-182">Надежные отправители и заблокированные отправители реплицированы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1656b-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="1656b-183">базовое делегирование и функциональную возможность отправки электронной почты от имени кого-либо.</span><span class="sxs-lookup"><span data-stu-id="1656b-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="1656b-184">У вас есть интегрированное решение для проверки подлинности с локальной смарт-картой или многофакторной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="1656b-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="1656b-185">Синхронизация фотографий, эскизов, конференц-залов и групп безопасности</span><span class="sxs-lookup"><span data-stu-id="1656b-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="1656b-186">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="1656b-186">Next step</span></span>

<span data-ttu-id="1656b-187">Когда вы будете готовы развернуть гибридное удостоверение, см. статью ["Подготовка к синхронизации каталогов".](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="1656b-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
  
