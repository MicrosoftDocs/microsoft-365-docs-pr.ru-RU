---
title: Установка политики срока действия паролей в организации
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Узнайте, как устанавливать политику срока действия паролей для организации в Центре администрирования Microsoft 365. '
ms.openlocfilehash: 053b3214862d477cbd122ff6336a6b53a98e5421
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597369"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="c0eb2-103">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="c0eb2-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c0eb2-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-104">The admin center is changing.</span></span> <span data-ttu-id="c0eb2-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c0eb2-106">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="c0eb2-107">Если вы обычный пользователь, у вас нет прав на установку бессрочного пароля.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="c0eb2-108">Попросите службу технической поддержки на работе или в учебном заведении выполнить за вас действия, указанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="c0eb2-109">Администраторы могут устанавливать срок действия пароля в днях или настраивать бессрочные пароли.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="c0eb2-110">По умолчанию срок действия паролей истекает через 90 дней.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="c0eb2-111">Современные исследования говорят о том, что изменение пароля, установленного в качестве обязательного, приносит больше вреда, чем пользы.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="c0eb2-112">Это приводит к тому, что пользователи выбирают ненадежные пароли, повторно используют или обновляют старые пароли, делая их уязвимыми для злоумышленников. </span><span class="sxs-lookup"><span data-stu-id="c0eb2-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="c0eb2-113">При установке неограниченного срока действия пароля рекомендуем включить [многофакторную проверку подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="c0eb2-114">Выполните указанные ниже действия, если вы хотите установить срок действия паролей пользователей в днях.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="c0eb2-115">Эти действия могут выполнять только [глобальные администраторы](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="c0eb2-116">В Центре администрирования выберите **Параметры** \> **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="c0eb2-117">Перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Безопасность и конфиденциальность</a>.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="c0eb2-118">Если вы не являетесь глобальным администратором, параметр "Безопасность и конфиденциальность" будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="c0eb2-119">Выберите **Политика срока действия паролей**</span><span class="sxs-lookup"><span data-stu-id="c0eb2-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="c0eb2-120">Если вы не хотите, чтобы пользователи могли менять пароли, установите флажок **Задать срок действия паролей пользователей в днях**.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="c0eb2-121">Укажите срок действия паролей.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-121">Type how often passwords should expire.</span></span> <span data-ttu-id="c0eb2-122">Выберите значение от 14 до 730 дней.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="c0eb2-123">Во втором поле укажите, за сколько дней до окончания действия пароля будет отправляться уведомление, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="c0eb2-124">Выберите значение от 1 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="c0eb2-125">После окончания срока действия пароля в правом нижнем углу экрана пользователя появится уведомление.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="c0eb2-126">Что важно знать об окончании срока действия паролей</span><span class="sxs-lookup"><span data-stu-id="c0eb2-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="c0eb2-127">Ниже приведены важные сведения о том, как эта функция работает по состоянию на январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="c0eb2-p107">Пользователям, применяющим только приложение Outlook, не потребуется сбрасывать свой пароль для Microsoft 365, пока не истечет срок его действия в кэше. Это может произойти через несколько дней после фактической даты окончания срока действия. На уровне администратора не существует обходного решения для этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="c0eb2-p108">Пользователи не получают уведомление о том, что срок действия их пароля истечет через X дней. Вам нужна эта возможность? **[Проголосуйте за нее здесь!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="c0eb2-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="c0eb2-134">Предотвращение повторного использования последнего пароля</span><span class="sxs-lookup"><span data-stu-id="c0eb2-134">Prevent last password from being used again</span></span>

<span data-ttu-id="c0eb2-135">Если вы хотите запретить пользователям повторно использовать старые пароли, это можно сделать, применив журнал паролей в локальной службе Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-135">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="c0eb2-136">Дополнительные сведения см. в разделе [Создание настраиваемой политики паролей](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-136">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="c0eb2-137">В Azure AD при изменении пароля пользователь не может повторно использовать последний пароль.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-137">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="c0eb2-138">Политика паролей применяется ко всем учетным записям пользователей, созданным и управляемым непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-138">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="c0eb2-139">Эта политика паролей не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-139">This password policy can't be modified.</span></span> <span data-ttu-id="c0eb2-140">См. раздел [Политика паролей Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-140">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="c0eb2-141">Синхронизация хэшей паролей пользователей из локальной службы каталогов Active Directory c Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="c0eb2-141">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="c0eb2-142">В этой статье описывается настройка политики срока действия паролей только для облачных пользователей (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-142">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="c0eb2-143">Она не применима к пользователям в гибридной среде, для которых используется синхронизация хэшей паролей, сквозная проверка подлинности или локальная служба федерации, например ADFS.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-143">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="c0eb2-144">Сведения о том, как синхронизировать хэши паролей пользователей из локального каталога Active Directory с Azure AD, см. в статье [Реализация синхронизации хэшей паролей с помощью Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-144">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>


## <a name="update-password-policy"></a><span data-ttu-id="c0eb2-145">Обновление политики паролей</span><span class="sxs-lookup"><span data-stu-id="c0eb2-145">Update password Policy</span></span>

<span data-ttu-id="c0eb2-146">Командлет Set-MsolPasswordPolicy обновляет политику паролей в указанном домене или клиенте.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-146">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="c0eb2-147">Два параметра являются обязательными: первый указывает время, в течение которого пароль остается действительным до того, как его потребуется изменить, а второй указывает количество дней до окончания срока действия пароля, который запускается при получении пользователями первого уведомления о том, что срок действия их пароля скоро истечет.</span><span class="sxs-lookup"><span data-stu-id="c0eb2-147">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="c0eb2-148">Сведения о том, как обновить политику паролей для определенного домена или клиента, см. в статье [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="c0eb2-148">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>
