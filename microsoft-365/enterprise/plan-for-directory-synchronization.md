---
title: Гибридное удостоверение и синхронизация каталогов для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
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
description: Описание синхронизации каталогов с Microsoft 365, очисткой доменных служб Active Directory и средством Azure Active Directory Connect.
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693209"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="402df-103">Гибридное удостоверение и синхронизация каталогов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="402df-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="402df-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="402df-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="402df-105">В зависимости от потребностей бизнеса и технических требований, наиболее распространенным выбором для корпоративных клиентов, использующих Microsoft 365, является гибридная модель идентификации и синхронизация службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="402df-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="402df-106">Синхронизация службы каталогов позволяет управлять удостоверениями в доменных службах Active Directory (AD DS), а все обновления учетных записей пользователей, групп и контактов синхронизируются с клиентом Azure Active Directory (Azure AD) вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="402df-107">Когда учетные записи пользователей AD DS синхронизируются впервые, им не назначается лицензия Microsoft 365 и не удается получить доступ к службам Microsoft 365, таким как электронная почта.</span><span class="sxs-lookup"><span data-stu-id="402df-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="402df-108">Сначала необходимо назначить им место использования.</span><span class="sxs-lookup"><span data-stu-id="402df-108">You must first assign them a usage location.</span></span> <span data-ttu-id="402df-109">Затем назначьте лицензию для этих учетных записей пользователей по отдельности или динамически с помощью членства в группе.</span><span class="sxs-lookup"><span data-stu-id="402df-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="402df-110">Проверка подлинности для гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="402df-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="402df-111">При использовании модели гибридной идентификации существует два типа проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="402df-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="402df-112">Управляемая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="402df-112">Managed authentication</span></span>

  <span data-ttu-id="402df-113">Azure AD обрабатывает процесс проверки подлинности с помощью локально сохраненной хешированной версии пароля или отправляет учетные данные в локальный агент программного обеспечения, чтобы пройти проверку подлинности в локальных доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="402df-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="402df-114">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="402df-114">Federated authentication</span></span>

  <span data-ttu-id="402df-115">Azure AD перенаправляет клиентский компьютер, запрашивающий проверку подлинности, другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="402df-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="402df-116">Управляемая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="402df-116">Managed authentication</span></span>

<span data-ttu-id="402df-117">Существует два типа управляемой проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="402df-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="402df-118">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="402df-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="402df-119">Проверка подлинности выполняется с помощью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="402df-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="402df-120">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="402df-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="402df-121">Проверка подлинности выполняется с помощью доменных служб Aсtive Directory в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="402df-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="402df-122">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="402df-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="402df-123">С помощью ФС вы синхронизируете учетные записи пользователей AD DS с Microsoft 365 и управляете локальными пользователями.</span><span class="sxs-lookup"><span data-stu-id="402df-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="402df-124">Хэши паролей пользователей синхронизируются из доменных служб Active Directory в Azure AD, чтобы пользователи могли использовать один и тот же пароль в локальной среде и в облаке.</span><span class="sxs-lookup"><span data-stu-id="402df-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="402df-125">Это самый простой способ включить проверку подлинности для удостоверений AD DS в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="402df-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Синхронизация хэша паролей (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="402df-127">Когда пароли изменяются или сбрасываются локально, новые хэши паролей синхронизируются с Azure AD, чтобы пользователи всегда могли использовать одинаковые пароли для облачных ресурсов и локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="402df-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="402df-128">Пароли пользователей никогда не отправляются в Azure AD или хранятся в службе Azure AD в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="402df-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="402df-129">Некоторые расширенные функции Azure AD, такие как защита идентификации, требуют ФС независимо от выбранного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="402df-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="402df-130">Чтобы узнать больше, ознакомьтесь со статьей [Выбор правильного метода проверки подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="402df-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="402df-131">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="402df-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="402df-132">ПТА предоставляет простую проверку паролей для служб проверки подлинности Azure AD с помощью программного агента, работающего на одном или нескольких локальных серверах, для проверки пользователей непосредственно в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="402df-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="402df-133">С помощью ПТА вы синхронизируете учетные записи пользователей AD DS с Microsoft 365 и управляете локальными пользователями.</span><span class="sxs-lookup"><span data-stu-id="402df-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Сквозная проверка подлинности (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="402df-135">ПТА позволяет пользователям входить как в локальные, так и в Microsoft 365 ресурсы и приложения, используя их локальную учетную запись и пароль.</span><span class="sxs-lookup"><span data-stu-id="402df-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="402df-136">Эта конфигурация проверяет пароли пользователей непосредственно для локальных доменных служб Active Directory без сохранения хеш-кодов паролей в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="402df-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="402df-137">ПТА также используется в организациях с требованиями к безопасности для немедленного применения локальных состояний учетных записей пользователей, политик паролей и часов входа.</span><span class="sxs-lookup"><span data-stu-id="402df-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="402df-138">Чтобы узнать больше, ознакомьтесь со статьей [Выбор правильного метода проверки подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="402df-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="402df-139">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="402df-139">Federated authentication</span></span>

<span data-ttu-id="402df-140">Федеративная проверка подлинности в основном используется для крупных организаций с более сложными требованиями к проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="402df-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="402df-141">Удостоверения доменных служб Active Directory синхронизируются с Microsoft 365, и учетные записи пользователей управляются локально.</span><span class="sxs-lookup"><span data-stu-id="402df-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="402df-142">При использовании федеративной проверки подлинности пользователи имеют один и тот же пароль в локальной среде и в облаке, и им не нужно повторно входить в систему, чтобы использовать Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="402df-143">Федеративная проверка подлинности может поддерживать дополнительные требования к проверке подлинности, такие как проверка подлинности на основе смарт-карт или третья многофакторная проверка подлинности и обычно требуется, когда в организациях нет требований проверки подлинности, изначально поддерживаемых Azure AD.</span><span class="sxs-lookup"><span data-stu-id="402df-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="402df-144">Чтобы узнать больше, ознакомьтесь со статьей [Выбор правильного метода проверки подлинности](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .</span><span class="sxs-lookup"><span data-stu-id="402df-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="402df-145">Сторонние поставщики проверки подлинности и идентификации</span><span class="sxs-lookup"><span data-stu-id="402df-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="402df-146">Локальные объекты каталогов могут синхронизироваться с Microsoft 365, а доступ к облачным ресурсам — главным образом сторонним поставщиком удостоверений (IdP).</span><span class="sxs-lookup"><span data-stu-id="402df-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="402df-147">Если в вашей организации используется стороннее решение Федерации, можно настроить вход с этим решением для Microsoft 365, предоставило, что стороннее решение совместимо с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="402df-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="402df-148">Чтобы узнать больше, ознакомьтесь со [списком совместимость Федерации Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) .</span><span class="sxs-lookup"><span data-stu-id="402df-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="402df-149">Подготовка AD DS</span><span class="sxs-lookup"><span data-stu-id="402df-149">AD DS Preparation</span></span>

<span data-ttu-id="402df-150">Для обеспечения беспрепятственного перехода на Microsoft 365 с помощью синхронизации необходимо подготовить лес доменных служб Active Directory, прежде чем приступать к развертыванию синхронизации каталогов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="402df-151">Подготовка каталогов должна сосредоточиться на следующих задачах:</span><span class="sxs-lookup"><span data-stu-id="402df-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="402df-152">Удалите повторяющиеся атрибуты **proxyAddress** и **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="402df-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="402df-153">Обновление пустых и недопустимых атрибутов **userPrincipalName** с допустимыми атрибутами **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="402df-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="402df-154">Удалите недопустимые и сомнительные символы в атрибутах **givenName**, фамилия ( **SN** ), **SamAccountName**, **DisplayName**, **mail**, **proxyAddresses**, **mailNickname**и **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="402df-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="402df-155">Подробнее о подготовке атрибутов можно узнать [в разделе List of Attributes, которые синхронизируются средством синхронизации Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span><span class="sxs-lookup"><span data-stu-id="402df-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="402df-156">Это те же атрибуты, которые синхронизируются с помощью Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="402df-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="402df-157">Рекомендации по развертыванию нескольких лесов</span><span class="sxs-lookup"><span data-stu-id="402df-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="402df-158">Для параметров нескольких лесов и единого входа используйте [выборочную установку Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span><span class="sxs-lookup"><span data-stu-id="402df-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="402df-159">Если в организации используется несколько лесов для проверки подлинности (лесов входа), настоятельно рекомендуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="402df-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="402df-160">**Рассмотрите вопрос консолидации лесов.**</span><span class="sxs-lookup"><span data-stu-id="402df-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="402df-161">В общем случае для поддержки нескольких лесов требуется дополнительная нагрузка.</span><span class="sxs-lookup"><span data-stu-id="402df-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="402df-162">Если в Организации не предусмотрены ограничения безопасности, которые определяют потребность в отдельных лесах, рекомендуется упростить локальную среду.</span><span class="sxs-lookup"><span data-stu-id="402df-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="402df-163">**Используйте только в основном лесе входа в систему.**</span><span class="sxs-lookup"><span data-stu-id="402df-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="402df-164">Рекомендуется развертывать Microsoft 365 только в основном лесе входа в систему для первоначального развертывания Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="402df-165">Если вы не можете консолидировать развертывание AD DS с несколькими лесами или используете другие службы каталогов для управления удостоверениями, их можно синхронизировать с помощью корпорации Майкрософт или партнера.</span><span class="sxs-lookup"><span data-stu-id="402df-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="402df-166">Для получения дополнительных сведений см. [топологии для Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) .</span><span class="sxs-lookup"><span data-stu-id="402df-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="402df-167">Компоненты, зависящие от синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="402df-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="402df-168">Синхронизация службы каталогов необходима для следующих функций и функций:</span><span class="sxs-lookup"><span data-stu-id="402df-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="402df-169">Единый вход в Azure AD (SSO)</span><span class="sxs-lookup"><span data-stu-id="402df-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="402df-170">Сосуществование Skype</span><span class="sxs-lookup"><span data-stu-id="402df-170">Skype coexistence</span></span>
- <span data-ttu-id="402df-171">Гибридное развертывание Exchange, в том числе:</span><span class="sxs-lookup"><span data-stu-id="402df-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="402df-172">Полный общий глобальный список адресов (GAL) между локальной средой Exchange и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="402df-173">синхронизацию данных глобального списка адресов из разных почтовых систем;</span><span class="sxs-lookup"><span data-stu-id="402df-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="402df-174">Возможность добавлять и удалять пользователей из служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="402df-175">Для этого требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="402df-175">This requires the following:</span></span>
  - <span data-ttu-id="402df-176">Двухсторонняя синхронизация должна быть настроена во время настройки синхронизации службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="402df-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="402df-177">По умолчанию средства синхронизации службы каталогов записывают данные каталога только в облако.</span><span class="sxs-lookup"><span data-stu-id="402df-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="402df-178">При настройке двусторонней синхронизации необходимо включить функцию обратной записи, чтобы в облако копировалось ограниченное количество атрибутов объектов, а затем они были записаны в локальные доменные службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="402df-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="402df-179">Обратная запись также называется гибридным режимом Exchange.</span><span class="sxs-lookup"><span data-stu-id="402df-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="402df-180">Локальное гибридное развертывание Exchange</span><span class="sxs-lookup"><span data-stu-id="402df-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="402df-181">Возможность перемещать некоторые почтовые ящики пользователей в Microsoft 365, сохраняя другие локальные почтовые ящики пользователей.</span><span class="sxs-lookup"><span data-stu-id="402df-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="402df-182">Надежные отправители и заблокированные отправители реплицируются в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402df-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="402df-183">базовое делегирование и функциональную возможность отправки электронной почты от имени кого-либо.</span><span class="sxs-lookup"><span data-stu-id="402df-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="402df-184">У вас есть интегрированная локальная смарт-карта или решение с многофакторной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="402df-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="402df-185">Синхронизация фотографий, эскизов, Конференц-залов и групп безопасности</span><span class="sxs-lookup"><span data-stu-id="402df-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="402df-186">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="402df-186">Next step</span></span>

<span data-ttu-id="402df-187">Когда вы будете готовы развернуть гибридную идентификацию, ознакомьтесь со статьей [Подготовка к подготовке пользователей](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="402df-187">When you are ready to deploy hybrid identity, see [prepare to provision users](prepare-for-directory-synchronization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="402df-188">См. также</span><span class="sxs-lookup"><span data-stu-id="402df-188">See also</span></span>

[<span data-ttu-id="402df-189">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="402df-189">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)

