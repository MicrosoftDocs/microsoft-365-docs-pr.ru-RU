---
title: Руководства по лаборатории тестирования для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/04/2019
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
description: С помощью этих руководств по лаборатории тестирования вы можете настраивать демонстрационные и экспериментальные среды, а также среды разработки и тестирования для Microsoft 365 корпоративный.
ms.openlocfilehash: dadde9d6366e2d5d12bf632d0b77bf60ba9cdbab
ms.sourcegitcommit: 78f2c5f89f4f59e4c1865369fc6ba82486881e8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2019
ms.locfileid: "37964433"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="614c9-103">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="614c9-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="614c9-p101">Руководства по лаборатории тестирования помогают быстро знакомиться с продуктами Майкрософт. Они содержат инструкции по настройке упрощенных и наглядных тестовых сред. Эти среды можно использовать для демонстрации и настройки, а также создания сложных экспериментов на протяжении срока действия пробной или платной подписки.</span><span class="sxs-lookup"><span data-stu-id="614c9-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="614c9-p102">Руководства по лаборатории тестирования делятся на модули. Каждый из них дополняет предыдущие, отображая несколько конфигураций, наиболее соответствующих вашим требованиям к учебной или тестовой конфигурации. Непосредственное знакомство с новым продуктом или сценарием помогает вам понять требования к его развертыванию, чтобы лучше спланировать его размещение в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="614c9-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="614c9-110">Кроме того, с помощью этих руководств можно создавать типичные среды для разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="614c9-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="614c9-112">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="614c9-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="614c9-113">[![Руководства по лаборатории тестирования для Microsoft 365 корпоративный](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="614c9-113">[![The Microsoft 365 Enterprise Test Lab Guide stack](./media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="614c9-114">Базовая настройка</span><span class="sxs-lookup"><span data-stu-id="614c9-114">Base configuration</span></span>

<span data-ttu-id="614c9-p103">Вначале нужно создать тестовую среду для [Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/), включающую Office 365 E5, Enterprise Mobility + Security (EMS) E5 и Windows 10 Корпоративная. Ви можете создать два типа базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="614c9-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="614c9-117">Используйте [простую базовую конфигурацию](lightweight-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный только в облачной среде, которая не включает каких-либо локальных компонентов.</span><span class="sxs-lookup"><span data-stu-id="614c9-117">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="614c9-118">Используйте [базовую конфигурацию "имитация предприятия"](simulated-ent-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный в гибридной облачной среде, содержащей локальные компоненты такие как домен доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="614c9-118">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="614c9-119">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="614c9-119">Identity</span></span>

<span data-ttu-id="614c9-120">Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="614c9-120">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="614c9-121">Синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="614c9-121">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="614c9-122">Включение и тестирование синхронизации службы каталогов на основе хэша пароля из контроллера домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="614c9-122">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="614c9-123">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="614c9-123">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="614c9-124">Включение и тестирование сквозной проверки подлинности на контроллере домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="614c9-124">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="614c9-125">Простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="614c9-125">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="614c9-126">Включение и тестирование простого единого входа (SSO) Azure AD с контроллером домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="614c9-126">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="614c9-127">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="614c9-127">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="614c9-128">Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="614c9-128">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="614c9-129">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="614c9-129">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="614c9-130">Блокирование учетных записей глобальных администраторов с помощью политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="614c9-130">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="614c9-131">Обратная запись пароля</span><span class="sxs-lookup"><span data-stu-id="614c9-131">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="614c9-132">Смена пароля учетной записи пользователя AD DS из Azure AD с помощью обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="614c9-132">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="614c9-133">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="614c9-133">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="614c9-134">Используйте функцию самостоятельного сброса пароля (SSPR) для сброса пароля.</span><span class="sxs-lookup"><span data-stu-id="614c9-134">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="614c9-135">Автоматическое лицензирование и членство в группах</span><span class="sxs-lookup"><span data-stu-id="614c9-135">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="614c9-136">Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.</span><span class="sxs-lookup"><span data-stu-id="614c9-136">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="614c9-137">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="614c9-137">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="614c9-138">Проверка текущих учетных записей пользователей на уязвимости.</span><span class="sxs-lookup"><span data-stu-id="614c9-138">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="614c9-139">Доступ к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="614c9-139">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="614c9-140">Создание среды для тестирования рекомендуемых конфигураций доступа к удостоверениям и устройствам и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="614c9-140">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="614c9-141">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="614c9-141">Mobile device management</span></span>

<span data-ttu-id="614c9-142">Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="614c9-142">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="614c9-143">Политики соответствия требованиям для устройств</span><span class="sxs-lookup"><span data-stu-id="614c9-143">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="614c9-144">Создайте группу пользователей и политику соответствия требованиям для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="614c9-144">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="614c9-145">Регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="614c9-145">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="614c9-146">Регистрация устройств с iOS или Android и удаленное управление ими.</span><span class="sxs-lookup"><span data-stu-id="614c9-146">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="614c9-147">Защита информации</span><span class="sxs-lookup"><span data-stu-id="614c9-147">Information protection</span></span>

<span data-ttu-id="614c9-148">Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="614c9-148">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="614c9-149">Усиленная защита Office 365</span><span class="sxs-lookup"><span data-stu-id="614c9-149">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="614c9-150">Настройка параметров для усиления защиты Office 365 и изучение встроенных средств безопасности.</span><span class="sxs-lookup"><span data-stu-id="614c9-150">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="614c9-151">Классификация данных</span><span class="sxs-lookup"><span data-stu-id="614c9-151">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="614c9-152">Настройка и присвоение метки Office 365 документу на сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="614c9-152">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="614c9-153">Управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="614c9-153">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="614c9-154">Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="614c9-154">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


