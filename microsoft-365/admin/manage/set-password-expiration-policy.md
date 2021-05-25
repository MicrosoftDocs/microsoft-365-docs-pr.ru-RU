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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Узнайте, как администратор может настроить политику срока действия паролей для вашей организации, учебного заведения или некоммерческой организации в Центре администрирования Microsoft 365.
ms.openlocfilehash: 7f12918211718b91313c0c89b11eaeb0a8cc3181
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635826"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="e4794-103">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="e4794-103">Set the password expiration policy for your organization</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e4794-104">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="e4794-104">Before you begin</span></span>

<span data-ttu-id="e4794-105">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="e4794-105">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e4794-106">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4794-106">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="e4794-107">[Что такое учетная запись администратора?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e4794-107">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="e4794-p102">Администраторы могут устанавливать срок действия пароля в днях или настраивать бессрочные пароли. По умолчанию для организации пароли являются бессрочными.</span><span class="sxs-lookup"><span data-stu-id="e4794-p102">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire. By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="e4794-110">Современные исследования говорят о том, что изменение пароля, установленного в качестве обязательного, приносит больше вреда, чем пользы.</span><span class="sxs-lookup"><span data-stu-id="e4794-110">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="e4794-111">Это приводит к тому, что пользователи выбирают ненадежные пароли, повторно используют или обновляют старые пароли, делая их уязвимыми для злоумышленников. </span><span class="sxs-lookup"><span data-stu-id="e4794-111">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="e4794-112">Мы рекомендуем включить [многофакторную проверку подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e4794-112">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="e4794-113">Чтобы получить дополнительные сведения о политике паролей, ознакомьтесь с [Рекомендациями по политике паролей](../misc/password-policy-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e4794-113">To learn more about password policy, check out [Password policy recommendations](../misc/password-policy-recommendations.md).</span></span>

<span data-ttu-id="e4794-114">Эти действия может выполнять только [глобальный администратор](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e4794-114">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="e4794-p104">Если вы обычный пользователь, у вас нет прав на установку бессрочного пароля. Попросите службу технической поддержки на работе или в учебном заведении выполнить за вас действия, указанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e4794-p104">If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="e4794-117">Настройка политики срока действия паролей</span><span class="sxs-lookup"><span data-stu-id="e4794-117">Set password expiration policy</span></span>

<span data-ttu-id="e4794-118">Выполните указанные ниже действия, если вы хотите установить срок действия паролей пользователей в днях.</span><span class="sxs-lookup"><span data-stu-id="e4794-118">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="e4794-119">В Центре администрирования выберите **Параметры** \> **Параметры организации**.</span><span class="sxs-lookup"><span data-stu-id="e4794-119">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="e4794-120">Перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Безопасность и конфиденциальность</a>.</span><span class="sxs-lookup"><span data-stu-id="e4794-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="e4794-121">Если вы не являетесь глобальным администратором, параметр "Безопасность и конфиденциальность" будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="e4794-121">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="e4794-122">Выберите **Политика срока действия паролей**</span><span class="sxs-lookup"><span data-stu-id="e4794-122">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="e4794-123">Если вы не хотите, чтобы пользователям пришлось менять пароли, снимите флажок **Задать срок действия паролей пользователей через несколько дней**.</span><span class="sxs-lookup"><span data-stu-id="e4794-123">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="e4794-p106">Укажите срок действия паролей. Выберите значение от 14 до 730 дней.</span><span class="sxs-lookup"><span data-stu-id="e4794-p106">Type how often passwords should expire. Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="e4794-126">Во втором поле укажите, за сколько дней до окончания действия пароля будет отправляться уведомление, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e4794-126">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="e4794-127">Выберите значение от 1 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="e4794-127">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="e4794-128">Что важно знать об окончании срока действия паролей</span><span class="sxs-lookup"><span data-stu-id="e4794-128">Important things you need to know about the password expiration feature</span></span>
  
<span data-ttu-id="e4794-p108">Пользователям, применяющим только приложение Outlook, не потребуется сбрасывать свой пароль для Microsoft 365, пока не истечет срок его действия в кэше. Это может произойти через несколько дней после фактической даты окончания срока действия. На уровне администратора не существует обходного решения для этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="e4794-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="e4794-132">Предотвращение повторного использования последнего пароля</span><span class="sxs-lookup"><span data-stu-id="e4794-132">Prevent last password from being used again</span></span>

<span data-ttu-id="e4794-133">Если вы хотите запретить пользователям повторно использовать старые пароли, это можно сделать, применив журнал паролей в локальной службе Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="e4794-133">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="e4794-134">Дополнительные сведения см. в разделе [Создание настраиваемой политики паролей](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="e4794-134">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="e4794-135">В Azure AD при изменении пароля пользователь не может повторно использовать последний пароль.</span><span class="sxs-lookup"><span data-stu-id="e4794-135">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="e4794-136">Политика паролей применяется ко всем учетным записям пользователей, созданным и управляемым непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e4794-136">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="e4794-137">Эта политика паролей не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="e4794-137">This password policy can't be modified.</span></span> <span data-ttu-id="e4794-138">См. раздел [Политика паролей Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="e4794-138">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="e4794-139">Синхронизация хэшей паролей пользователей из локальной службы каталогов Active Directory c Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="e4794-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="e4794-140">В этой статье описывается настройка политики срока действия паролей только для облачных пользователей (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e4794-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="e4794-141">Она не применима к пользователям в гибридной среде, для которых используется синхронизация хэшей паролей, сквозная проверка подлинности или локальная служба федерации, например ADFS.</span><span class="sxs-lookup"><span data-stu-id="e4794-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="e4794-142">Сведения о том, как синхронизировать хэши паролей пользователей из локального каталога Active Directory с Azure AD, см. в статье [Реализация синхронизации хэшей паролей с помощью Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="e4794-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="e4794-143">Политики паролей и ограничения учетных записей в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e4794-143">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="e4794-144">Вы можете настроить дополнительные политики и ограничения для паролей в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e4794-144">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="e4794-145">Дополнительные сведения см. в статье [Политики паролей и ограничения учетных записей в Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="e4794-145">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="e4794-146">Обновление политики паролей</span><span class="sxs-lookup"><span data-stu-id="e4794-146">Update password Policy</span></span>

<span data-ttu-id="e4794-p113">Командлет Set-MsolPasswordPolicy обновляет политику паролей в указанном домене или клиенте. Два параметра являются обязательными: первый указывает время, в течение которого пароль остается действительным до того, как его потребуется изменить, а второй указывает количество дней до окончания срока действия пароля, который запускается при получении пользователями первого уведомления о том, что срок действия их пароля скоро истечет.</span><span class="sxs-lookup"><span data-stu-id="e4794-p113">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant. Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="e4794-149">Сведения о том, как обновить политику паролей для определенного домена или клиента, см. в статье [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e4794-149">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="e4794-150">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="e4794-150">Related content</span></span>

<span data-ttu-id="e4794-151">[Предоставление пользователям прав на самостоятельный сброс пароля](../add-users/let-users-reset-passwords.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="e4794-151">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="e4794-152">[Сброс паролей](../add-users/reset-passwords.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="e4794-152">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>