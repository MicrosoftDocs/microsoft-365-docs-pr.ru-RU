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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Узнайте, как устанавливать политику срока действия паролей для организации в Центре администрирования Microsoft 365. '
ms.openlocfilehash: dd925ee3a5d2aadb07dceed5a0e896e77921e2a1
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901014"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="8a31a-103">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="8a31a-103">Set the password expiration policy for your organization</span></span>

<span data-ttu-id="8a31a-104">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="8a31a-104">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="8a31a-105">Если вы обычный пользователь, у вас нет прав на установку бессрочного пароля.</span><span class="sxs-lookup"><span data-stu-id="8a31a-105">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="8a31a-106">Попросите службу технической поддержки на работе или в учебном заведении выполнить за вас действия, указанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8a31a-106">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="8a31a-107">Администраторы могут устанавливать срок действия пароля в днях или настраивать бессрочные пароли.</span><span class="sxs-lookup"><span data-stu-id="8a31a-107">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="8a31a-108">По умолчанию срок действия паролей истекает через 90 дней.</span><span class="sxs-lookup"><span data-stu-id="8a31a-108">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="8a31a-109">Современные исследования говорят о том, что изменение пароля, установленного в качестве обязательного, приносит больше вреда, чем пользы.</span><span class="sxs-lookup"><span data-stu-id="8a31a-109">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="8a31a-110">Это приводит к тому, что пользователи выбирают ненадежные пароли, повторно используют или обновляют старые пароли, делая их уязвимыми для злоумышленников. </span><span class="sxs-lookup"><span data-stu-id="8a31a-110">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="8a31a-111">При установке неограниченного срока действия пароля рекомендуем включить [многофакторную проверку подлинности](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8a31a-111">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="8a31a-112">Выполните указанные ниже действия, если вы хотите установить срок действия паролей пользователей в днях.</span><span class="sxs-lookup"><span data-stu-id="8a31a-112">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8a31a-113">Эти действия могут выполнять только [глобальные администраторы](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8a31a-113">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="8a31a-114">В Центре администрирования выберите **Параметры** \> **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="8a31a-114">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="8a31a-115">Перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Безопасность и конфиденциальность</a>.</span><span class="sxs-lookup"><span data-stu-id="8a31a-115">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="8a31a-116">Если вы не являетесь глобальным администратором, параметр "Безопасность и конфиденциальность" будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="8a31a-116">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="8a31a-117">Выберите **Политика срока действия паролей**</span><span class="sxs-lookup"><span data-stu-id="8a31a-117">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="8a31a-118">Если вы не хотите, чтобы пользователи могли менять пароли, установите флажок **Задать срок действия паролей пользователей в днях**.</span><span class="sxs-lookup"><span data-stu-id="8a31a-118">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="8a31a-119">Укажите срок действия паролей.</span><span class="sxs-lookup"><span data-stu-id="8a31a-119">Type how often passwords should expire.</span></span> <span data-ttu-id="8a31a-120">Выберите значение от 14 до 730 дней.</span><span class="sxs-lookup"><span data-stu-id="8a31a-120">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="8a31a-121">Во втором поле укажите, за сколько дней до окончания действия пароля будет отправляться уведомление, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8a31a-121">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="8a31a-122">Выберите значение от 1 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8a31a-122">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="8a31a-123">После окончания срока действия пароля в правом нижнем углу экрана пользователя появится уведомление.</span><span class="sxs-lookup"><span data-stu-id="8a31a-123">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="8a31a-124">Что важно знать об окончании срока действия паролей</span><span class="sxs-lookup"><span data-stu-id="8a31a-124">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="8a31a-125">Ниже приведены важные сведения о том, как эта функция работает по состоянию на январь 2018 г.</span><span class="sxs-lookup"><span data-stu-id="8a31a-125">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="8a31a-p106">Пользователям, применяющим только приложение Outlook, не потребуется сбрасывать свой пароль для Microsoft 365, пока не истечет срок его действия в кэше. Это может произойти через несколько дней после фактической даты окончания срока действия. На уровне администратора не существует обходного решения для этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="8a31a-p106">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="8a31a-p107">Пользователи не получают уведомление о том, что срок действия их пароля истечет через X дней. Вам нужна эта возможность? **[Проголосуйте за нее здесь!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="8a31a-p107">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="8a31a-132">Предотвращение повторного использования последнего пароля</span><span class="sxs-lookup"><span data-stu-id="8a31a-132">Prevent last password from being used again</span></span>

<span data-ttu-id="8a31a-133">Если вы хотите запретить пользователям повторно использовать старые пароли, это можно сделать в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8a31a-133">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="8a31a-134">См. статью [Вести журнал паролей](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span><span class="sxs-lookup"><span data-stu-id="8a31a-134">See [Enforce password history](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span></span>

<span data-ttu-id="8a31a-135">Кроме того, если сотрудник использовал мобильное устройство для доступа к Microsoft 365, можно очистить это устройство, чтобы убедиться, что пароль больше не хранится на устройстве и не может быть использован повторно.</span><span class="sxs-lookup"><span data-stu-id="8a31a-135">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="8a31a-136">Дополнительные сведения см. в статье [Очистка и блокирование мобильного устройства бывшего сотрудника](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="8a31a-136">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="8a31a-137">Синхронизация хэшей паролей пользователей из локальной службы каталогов Active Directory c Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="8a31a-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="8a31a-138">В этой статье описывается настройка политики срока действия паролей только для облачных пользователей (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8a31a-138">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="8a31a-139">Она не применима к пользователям в гибридной среде, для которых используется синхронизация хэшей паролей, сквозная проверка подлинности или локальная служба федерации, например ADFS.</span><span class="sxs-lookup"><span data-stu-id="8a31a-139">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="8a31a-140">Сведения о том, как синхронизировать хэши паролей пользователей из локального каталога Active Directory с Azure AD, см. в статье [Реализация синхронизации хэшей паролей с помощью Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="8a31a-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
