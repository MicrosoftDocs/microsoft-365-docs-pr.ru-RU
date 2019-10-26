---
title: Руководства по лаборатории тестирования для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
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
ms.openlocfilehash: 082d110ca7b25d3613ee276b30066683cd0232b5
ms.sourcegitcommit: 64a21c59d31a283ccbe87d16f0a174998e3aeba8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "37733430"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="5c223-103">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="5c223-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="5c223-p101">Руководства по лаборатории тестирования помогают быстро знакомиться с продуктами Майкрософт. Они содержат инструкции по настройке упрощенных и наглядных тестовых сред. Эти среды можно использовать для демонстрации и настройки, а также создания сложных экспериментов на протяжении срока действия пробной или платной подписки.</span><span class="sxs-lookup"><span data-stu-id="5c223-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="5c223-p102">Руководства по лаборатории тестирования делятся на модули. Каждый из них дополняет предыдущие, отображая несколько конфигураций, наиболее соответствующих вашим требованиям к учебной или тестовой конфигурации. Непосредственное знакомство с новым продуктом или сценарием помогает вам понять требования к его развертыванию, чтобы лучше спланировать его размещение в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="5c223-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="5c223-110">Кроме того, с помощью этих руководств можно создавать типичные среды для разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="5c223-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5c223-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="5c223-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="5c223-113">Базовая настройка</span><span class="sxs-lookup"><span data-stu-id="5c223-113">Base configuration</span></span>

<span data-ttu-id="5c223-p103">Вначале нужно создать тестовую среду для [Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/), включающую Office 365 E5, Enterprise Mobility + Security (EMS) E5 и Windows 10 Корпоративная. Ви можете создать два типа базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5c223-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="5c223-116">Используйте [простую базовую конфигурацию](lightweight-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный только в облачной среде, которая не включает каких-либо локальных компонентов.</span><span class="sxs-lookup"><span data-stu-id="5c223-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="5c223-117">Используйте [базовую конфигурацию "имитация предприятия"](simulated-ent-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный в гибридной облачной среде, содержащей локальные компоненты такие как домен доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5c223-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="5c223-118">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="5c223-118">Identity</span></span>

<span data-ttu-id="5c223-119">Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="5c223-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="5c223-120">Синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="5c223-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="5c223-121">Включение и тестирование синхронизации службы каталогов на основе хэша пароля из контроллера домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="5c223-121">Enable and test password hash-based directory synchronization from a AD DS domain controller.</span></span>

- [<span data-ttu-id="5c223-122">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="5c223-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="5c223-123">Включение и тестирование сквозной проверки подлинности на контроллере домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="5c223-123">Enable and test pass-through authentication to a AD DS domain controller.</span></span>

- [<span data-ttu-id="5c223-124">Простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c223-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="5c223-125">Включение и тестирование простого единого входа (SSO) Azure AD с контроллером домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="5c223-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a AD DS domain controller.</span></span>

- [<span data-ttu-id="5c223-126">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="5c223-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="5c223-127">Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5c223-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="5c223-128">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="5c223-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="5c223-129">Блокирование учетных записей глобальных администраторов с помощью политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="5c223-129">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="5c223-130">Обратная запись пароля</span><span class="sxs-lookup"><span data-stu-id="5c223-130">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="5c223-131">Смена пароля учетной записи пользователя AD DS из Azure AD с помощью обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="5c223-131">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="5c223-132">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="5c223-132">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="5c223-133">Используйте функцию самостоятельного сброса пароля (SSPR) для сброса пароля.</span><span class="sxs-lookup"><span data-stu-id="5c223-133">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="5c223-134">Автоматическое лицензирование и членство в группах</span><span class="sxs-lookup"><span data-stu-id="5c223-134">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="5c223-135">Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.</span><span class="sxs-lookup"><span data-stu-id="5c223-135">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="5c223-136">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c223-136">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="5c223-137">Проверка текущих учетных записей пользователей на уязвимости.</span><span class="sxs-lookup"><span data-stu-id="5c223-137">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="5c223-138">Доступ к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="5c223-138">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="5c223-139">Создание среды для тестирования рекомендуемых конфигураций доступа к удостоверениям и устройствам и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="5c223-139">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="5c223-140">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5c223-140">Mobile device management</span></span>

<span data-ttu-id="5c223-141">Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="5c223-141">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="5c223-142">Политики соответствия требованиям для устройств</span><span class="sxs-lookup"><span data-stu-id="5c223-142">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="5c223-143">Создайте группу пользователей и политику соответствия требованиям для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5c223-143">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="5c223-144">Регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="5c223-144">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="5c223-145">Регистрация устройств с iOS или Android и удаленное управление ими.</span><span class="sxs-lookup"><span data-stu-id="5c223-145">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="5c223-146">Защита информации</span><span class="sxs-lookup"><span data-stu-id="5c223-146">Information protection</span></span>

<span data-ttu-id="5c223-147">Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="5c223-147">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="5c223-148">Усиленная защита Office 365</span><span class="sxs-lookup"><span data-stu-id="5c223-148">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="5c223-149">Настройка параметров для усиления защиты Office 365 и изучение встроенных средств безопасности.</span><span class="sxs-lookup"><span data-stu-id="5c223-149">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="5c223-150">Классификация данных</span><span class="sxs-lookup"><span data-stu-id="5c223-150">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="5c223-151">Настройка и присвоение метки Office 365 документу на сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5c223-151">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="5c223-152">Управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="5c223-152">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="5c223-153">Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c223-153">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c223-154">См. также</span><span class="sxs-lookup"><span data-stu-id="5c223-154">See also</span></span>

[<span data-ttu-id="5c223-155">Тестирование Office 365 с помощью руководств по лабораторному тестированию для внедрения в облако</span><span class="sxs-lookup"><span data-stu-id="5c223-155">Test Office 365 with cloud adoption TLGs</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
