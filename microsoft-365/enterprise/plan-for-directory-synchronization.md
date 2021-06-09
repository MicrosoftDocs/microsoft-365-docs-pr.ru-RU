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
description: Описывает синхронизацию каталогов с Microsoft 365, очисткой доменных служб Active Directory и Azure Active Directory Подключение инструментом.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927548"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="26103-103">Гибридная синхронизация удостоверений и каталогов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26103-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="26103-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="26103-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="26103-105">В зависимости от бизнес-потребностей и технических требований гибридная модель удостоверений и синхронизация каталогов является наиболее распространенным выбором для корпоративных клиентов, которые принимают Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26103-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="26103-106">Синхронизация каталогов позволяет управлять удостоверениями в службах домена Active Directory (AD DS), а все обновления учетных записей пользователей, групп и контактов синхронизируются с клиентом Azure Active Directory Azure AD вашей Microsoft 365 подписки.</span><span class="sxs-lookup"><span data-stu-id="26103-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="26103-107">Когда учетные записи пользователей AD DS синхронизируются впервые, они не получают автоматически Microsoft 365 лицензии и не могут получить доступ к Microsoft 365, например электронной почте.</span><span class="sxs-lookup"><span data-stu-id="26103-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="26103-108">Сначала необходимо назначить им расположение использования.</span><span class="sxs-lookup"><span data-stu-id="26103-108">You must first assign them a usage location.</span></span> <span data-ttu-id="26103-109">Затем назначьте лицензию этим учетным записям пользователей в индивидуальном или динамическом виде с помощью членства в группе.</span><span class="sxs-lookup"><span data-stu-id="26103-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="26103-110">Проверка подлинности для гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="26103-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="26103-111">Существует два типа проверки подлинности при использовании гибридной модели удостоверений:</span><span class="sxs-lookup"><span data-stu-id="26103-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="26103-112">Управляемая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-112">Managed authentication</span></span>

  <span data-ttu-id="26103-113">Azure AD обрабатывает процесс проверки подлинности с помощью локально хранимой версии пароля или отправляет учетные данные локальному программному агенту для проверки подлинности локальной службой AD DS.</span><span class="sxs-lookup"><span data-stu-id="26103-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="26103-114">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="26103-114">Federated authentication</span></span>

  <span data-ttu-id="26103-115">Azure AD перенаправляет клиентский компьютер, запрашивающий проверку подлинности, другому поставщику удостоверений.</span><span class="sxs-lookup"><span data-stu-id="26103-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="26103-116">Управляемая проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-116">Managed authentication</span></span>

<span data-ttu-id="26103-117">Существует два типа управляемой проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="26103-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="26103-118">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="26103-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="26103-119">Проверка подлинности выполняется с помощью Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="26103-120">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="26103-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="26103-121">Проверка подлинности выполняется с помощью доменных служб Aсtive Directory в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="26103-122">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="26103-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="26103-123">С помощью PHS вы синхронизируете учетные записи пользователей AD DS с Microsoft 365 и управлять пользователями на месте.</span><span class="sxs-lookup"><span data-stu-id="26103-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="26103-124">Хеши паролей пользователей синхронизируются из AD DS в Azure AD, чтобы у пользователей был один и тот же пароль в локальном и облачном помещении.</span><span class="sxs-lookup"><span data-stu-id="26103-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="26103-125">Это самый простой способ включить проверку подлинности удостоверений AD DS в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Синхронизация хэша паролей (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="26103-127">При изменении или сбросе паролей на локальном уровне новые хеши паролей синхронизируются с Azure AD, чтобы пользователи всегда могли использовать один и тот же пароль для облачных ресурсов и локального ресурса.</span><span class="sxs-lookup"><span data-stu-id="26103-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="26103-128">Пароли пользователей никогда не отправляются в Azure AD или хранятся в Azure AD в понятном тексте.</span><span class="sxs-lookup"><span data-stu-id="26103-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="26103-129">Некоторые премиум-функции Azure AD, такие как Защита удостоверений, требуют PHS независимо от выбранного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="26103-130">Подробнее [см. в подборе](/azure/active-directory/hybrid/choose-ad-authn) правильного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="26103-131">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="26103-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="26103-132">PTA предоставляет простую проверку пароля для служб проверки подлинности Azure AD с помощью агента программного обеспечения, который работает на одном или несколько локальном сервере для проверки пользователей непосредственно с помощью AD DS.</span><span class="sxs-lookup"><span data-stu-id="26103-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="26103-133">С помощью PTA вы синхронизируете учетные записи пользователей AD DS с Microsoft 365 и управлять пользователями на месте.</span><span class="sxs-lookup"><span data-stu-id="26103-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Сквозная проверка подлинности (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="26103-135">PTA позволяет пользователям войти в локальное и Microsoft 365 и приложения с помощью локальной учетной записи и пароля.</span><span class="sxs-lookup"><span data-stu-id="26103-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="26103-136">Эта конфигурация проверяет пароли пользователей непосредственно к локальной AD DS без хранения хеши паролей в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="26103-137">PTA также для организаций с требованием безопасности немедленно применять локальное состояния учетных записей пользователей, политики паролей и часы логона.</span><span class="sxs-lookup"><span data-stu-id="26103-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="26103-138">Подробнее [см. в подборе](/azure/active-directory/hybrid/choose-ad-authn) правильного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="26103-139">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="26103-139">Federated authentication</span></span>

<span data-ttu-id="26103-140">Федерационная проверка подлинности в основном предназначена для крупных корпоративных организаций с более сложными требованиями к проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="26103-141">Удостоверения AD DS синхронизируются с Microsoft 365, а учетные записи пользователей управляются локально.</span><span class="sxs-lookup"><span data-stu-id="26103-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="26103-142">С федерацией проверки подлинности пользователи имеют одинаковый пароль на локальной основе и в облаке, и им не нужно снова входить, чтобы использовать Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26103-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="26103-143">Федеративная проверка подлинности может поддерживать дополнительные требования к проверке подлинности, например проверку подлинности на основе смарт-карт или сторонней многофакторной проверки подлинности, и обычно требуется, если у организаций есть требование проверки подлинности, не поддерживаемые Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="26103-144">Подробнее [см. в подборе](/azure/active-directory/hybrid/choose-ad-authn) правильного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="26103-145">Сторонние поставщики проверки подлинности и удостоверений</span><span class="sxs-lookup"><span data-stu-id="26103-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="26103-146">Объекты локального каталога могут синхронизироваться с Microsoft 365 и доступ к облачным ресурсам в основном управляется сторонним поставщиком удостоверений (IdP).</span><span class="sxs-lookup"><span data-stu-id="26103-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="26103-147">Если ваша организация использует сторонное решение федерации, вы можете настроить вход с этим решением для Microsoft 365 при условии, что решение федерации сторонних организаций совместимо с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="26103-148">Дополнительные дополнительные возможности см. в списке совместимости федерации [Azure AD.](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility)</span><span class="sxs-lookup"><span data-stu-id="26103-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="26103-149">Подготовка AD DS</span><span class="sxs-lookup"><span data-stu-id="26103-149">AD DS Preparation</span></span>

<span data-ttu-id="26103-150">Чтобы обеспечить плавный переход к Microsoft 365 с помощью синхронизации, необходимо подготовить лес AD DS, прежде чем приступить к развертыванию синхронизации Microsoft 365 каталогов.</span><span class="sxs-lookup"><span data-stu-id="26103-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="26103-151">Подготовка каталога должна быть сосредоточена на следующих задачах:</span><span class="sxs-lookup"><span data-stu-id="26103-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="26103-152">Удалите **дублирующиеся атрибуты proxyAddress** и **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="26103-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="26103-153">Обновление пустых и **недействительных атрибутов userPrincipalName с** допустимыми атрибутами **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="26103-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="26103-154">Удаление недействительных и сомнительных символов в **givenName**, фамилия ( **sn** ), **sAMAccountName**, **displayName**, **почта**, **proxyAddresses**, **mailNickname** и **userPrincipalName** атрибуты.</span><span class="sxs-lookup"><span data-stu-id="26103-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="26103-155">Подробные сведения о подготовке атрибутов см. в списке атрибутов, синхронизируются с Azure Active Directory [Sync Tool.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="26103-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="26103-156">Это те же атрибуты, которые Подключение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26103-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="26103-157">Аспекты развертывания с несколькими лесами</span><span class="sxs-lookup"><span data-stu-id="26103-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="26103-158">Для нескольких лесов и параметров SSO используйте настраиваемую установку [azure AD Подключение.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="26103-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="26103-159">Если в организации имеется несколько лесов для проверки подлинности (леса с логотипом), настоятельно рекомендуется следующее:</span><span class="sxs-lookup"><span data-stu-id="26103-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="26103-160">**Рассмотрите возможность консолидации лесов.**</span><span class="sxs-lookup"><span data-stu-id="26103-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="26103-161">Как правило, существует больше накладных расходов, необходимых для поддержания нескольких лесов.</span><span class="sxs-lookup"><span data-stu-id="26103-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="26103-162">Если в организации нет ограничений безопасности, которые диктуют необходимость отдельных лесов, рассмотрите возможность упрощения локальной среды.</span><span class="sxs-lookup"><span data-stu-id="26103-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="26103-163">**Используйте только в основном лесу с логотипом.**</span><span class="sxs-lookup"><span data-stu-id="26103-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="26103-164">Развертывание Microsoft 365 только в основном лесу логотипов для первоначального развертывания Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26103-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="26103-165">Если вы не можете консолидировать развертывание AD DS с несколькими лесами или использовать другие службы каталогов для управления удостоверениями, вы можете синхронизировать их с помощью Microsoft или партнера.</span><span class="sxs-lookup"><span data-stu-id="26103-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="26103-166">Дополнительные [сведения см. в Подключение topologies for Azure AD.](/azure/active-directory/hybrid/plan-connect-topologies)</span><span class="sxs-lookup"><span data-stu-id="26103-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="26103-167">Функции, зависящие от синхронизации каталогов</span><span class="sxs-lookup"><span data-stu-id="26103-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="26103-168">Синхронизация каталогов необходима для следующих функций и функций:</span><span class="sxs-lookup"><span data-stu-id="26103-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="26103-169">Azure AD Бесшовный Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="26103-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="26103-170">Skype сосуществования</span><span class="sxs-lookup"><span data-stu-id="26103-170">Skype coexistence</span></span>
- <span data-ttu-id="26103-171">Exchange гибридного развертывания, в том числе:</span><span class="sxs-lookup"><span data-stu-id="26103-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="26103-172">Полностью общий глобальный список адресов (GAL) между локальной Exchange и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26103-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="26103-173">синхронизацию данных глобального списка адресов из разных почтовых систем;</span><span class="sxs-lookup"><span data-stu-id="26103-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="26103-174">Возможность добавлять пользователей к пользователям и удалять их из Microsoft 365 служб.</span><span class="sxs-lookup"><span data-stu-id="26103-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="26103-175">Для этого необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="26103-175">This requires the following:</span></span>
  - <span data-ttu-id="26103-176">При настройке синхронизации каталогов необходимо настроить двунастройную синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="26103-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="26103-177">По умолчанию средства синхронизации каталогов записывают сведения о каталогах только в облако.</span><span class="sxs-lookup"><span data-stu-id="26103-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="26103-178">При настройке двунастройной синхронизации вы включаете функции обратного копирования, чтобы ограниченное число атрибутов объектов скопировалось из облака, а затем было записано обратно в локальное AD DS.</span><span class="sxs-lookup"><span data-stu-id="26103-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="26103-179">Записи обратно также называются гибридным Exchange режиме.</span><span class="sxs-lookup"><span data-stu-id="26103-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="26103-180">Локальное Exchange гибридное развертывание</span><span class="sxs-lookup"><span data-stu-id="26103-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="26103-181">Возможность перемещения некоторых почтовых ящиков пользователей в Microsoft 365, сохраняя при этом другие почтовые ящики пользователей в локальном помещении.</span><span class="sxs-lookup"><span data-stu-id="26103-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="26103-182">Сейф и заблокированные отправители реплицированы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26103-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="26103-183">базовое делегирование и функциональную возможность отправки электронной почты от имени кого-либо.</span><span class="sxs-lookup"><span data-stu-id="26103-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="26103-184">У вас есть интегрированное локальное решение для проверки подлинности или многофакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="26103-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="26103-185">Синхронизация фотографий, эскизов, конференц-залов и групп безопасности</span><span class="sxs-lookup"><span data-stu-id="26103-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="26103-186">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="26103-186">Next step</span></span>

<span data-ttu-id="26103-187">Когда вы готовы развернуть гибридную идентификацию, см. [в статью подготовка к синхронизации каталогов.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="26103-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
