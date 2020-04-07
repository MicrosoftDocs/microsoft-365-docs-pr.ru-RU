---
title: Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: С помощью этих руководств по лаборатории тестирования вы можете настраивать демонстрационные и экспериментальные среды, а также среды разработки и тестирования для Microsoft 365 на крупных предприятиях.
ms.openlocfilehash: 1ea41cd3553c70b2a8bb99e08da43fd45b1aa558
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153920"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="ca1bf-103">Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях</span><span class="sxs-lookup"><span data-stu-id="ca1bf-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="ca1bf-104">*Это относится к Microsoft 365 для крупных предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="ca1bf-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ca1bf-p101">Руководства по лаборатории тестирования помогают быстро знакомиться с продуктами Майкрософт. Они содержат инструкции по настройке упрощенных и наглядных тестовых сред. Эти среды можно использовать для демонстрации и настройки, а также создания сложных экспериментов на протяжении срока действия пробной или платной подписки.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="ca1bf-p102">Руководства по лаборатории тестирования делятся на модули. Каждый из них дополняет предыдущие, отображая несколько конфигураций, наиболее соответствующих вашим требованиям к учебной или тестовой конфигурации. Непосредственное знакомство с новым продуктом или сценарием помогает вам понять требования к его развертыванию, чтобы лучше спланировать его размещение в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="ca1bf-111">Кроме того, с помощью этих руководств можно создавать типичные среды для разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="ca1bf-113">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="ca1bf-114">[![Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="ca1bf-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="ca1bf-115">Базовая настройка</span><span class="sxs-lookup"><span data-stu-id="ca1bf-115">Base configuration</span></span>

<span data-ttu-id="ca1bf-p103">Вначале нужно создать тестовую среду для [Microsoft 365 на крупных предприятиях](https://docs.microsoft.com/microsoft-365-enterprise/), включающую Office 365 E5, Enterprise Mobility + Security (EMS) E5 и Windows 10 Корпоративная. Вы можете создать два типа базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-p103">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="ca1bf-118">Используйте [простую базовую конфигурацию](lightweight-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 для крупных предприятий только в облачной среде, которая не включает каких-либо локальных компонентов.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="ca1bf-119">Используйте [базовую конфигурацию "имитация предприятия"](simulated-ent-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 для крупных предприятий в гибридной облачной среде, содержащей локальные компоненты, такие как домен доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="ca1bf-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="ca1bf-120">Кроме того, вы можете создавать тестовые среды для Office 365 E5, не добавляя лицензию Microsoft 365 E5 в пробную или рабочую тестовую среду.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="ca1bf-121">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="ca1bf-121">Identity</span></span>

<span data-ttu-id="ca1bf-122">Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ca1bf-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="ca1bf-123">Синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="ca1bf-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="ca1bf-124">Включение и тестирование синхронизации службы каталогов на основе хэша пароля из контроллера домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="ca1bf-125">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ca1bf-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="ca1bf-126">Включение и тестирование сквозной проверки подлинности на контроллере домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="ca1bf-127">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ca1bf-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="ca1bf-128">Включение и тестирование федеративной проверки подлинности на контроллере домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="ca1bf-129">Простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="ca1bf-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="ca1bf-130">Включение и тестирование простого единого входа (SSO) Azure AD с контроллером домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="ca1bf-131">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ca1bf-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="ca1bf-132">Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="ca1bf-133">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="ca1bf-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="ca1bf-134">Блокирование учетных записей глобальных администраторов с помощью политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-134">Lock down your global administrator accounts with Conditional Access policies.</span></span>

- [<span data-ttu-id="ca1bf-135">Обратная запись пароля</span><span class="sxs-lookup"><span data-stu-id="ca1bf-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="ca1bf-136">Смена пароля учетной записи пользователя AD DS из Azure AD с помощью обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="ca1bf-137">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="ca1bf-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="ca1bf-138">Используйте функцию самостоятельного сброса пароля (SSPR) для сброса пароля.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="ca1bf-139">Автоматическое лицензирование и членство в группах</span><span class="sxs-lookup"><span data-stu-id="ca1bf-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="ca1bf-140">Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="ca1bf-141">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="ca1bf-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="ca1bf-142">Проверка текущих учетных записей пользователей на уязвимости.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="ca1bf-143">Доступ к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="ca1bf-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="ca1bf-144">Создание среды для тестирования рекомендуемых конфигураций доступа к удостоверениям и устройствам и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-144">Create an environment to test recommended identity and device access configurations and Conditional Access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="ca1bf-145">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="ca1bf-145">Mobile device management</span></span>

<span data-ttu-id="ca1bf-146">Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ca1bf-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="ca1bf-147">Политики соответствия требованиям для устройств</span><span class="sxs-lookup"><span data-stu-id="ca1bf-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="ca1bf-148">Создайте группу пользователей и политику соответствия требованиям для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="ca1bf-149">Регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="ca1bf-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="ca1bf-150">Регистрация устройств с iOS или Android и удаленное управление ими.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="ca1bf-151">Защита информации</span><span class="sxs-lookup"><span data-stu-id="ca1bf-151">Information protection</span></span>

<span data-ttu-id="ca1bf-152">Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ca1bf-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="ca1bf-153">Усиленная защита Office 365</span><span class="sxs-lookup"><span data-stu-id="ca1bf-153">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="ca1bf-154">Настройка параметров для усиления защиты Office 365 и изучение встроенных средств безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-154">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="ca1bf-155">Классификация данных</span><span class="sxs-lookup"><span data-stu-id="ca1bf-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="ca1bf-156">Настройка и присвоение метки Office 365 документу на сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-156">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="ca1bf-157">Управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="ca1bf-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="ca1bf-158">Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca1bf-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


