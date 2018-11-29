---
title: Руководства по лаборатории тестирования для Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: С помощью этих руководств по лаборатории тестирования вы можете настраивать демонстрационные и экспериментальные среды, а также среды разработки и тестирования для Microsoft 365 корпоративный.
ms.openlocfilehash: df723647748532936e40bbdb4e34ff698b9fa650
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870939"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="e9edc-103">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e9edc-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="e9edc-p101">Руководства по лаборатории тестирования помогают быстро знакомиться с продуктами Майкрософт. Они содержат инструкции по настройке упрощенных и наглядных тестовых сред. Эти среды можно использовать для демонстрации и настройки, а также создания сложных экспериментов на протяжении срока действия пробной или платной подписки.</span><span class="sxs-lookup"><span data-stu-id="e9edc-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="e9edc-p102">Руководства по лаборатории тестирования делятся на модули. Каждый из них дополняет предыдущие, отображая несколько конфигураций, наиболее соответствующих вашим требованиям к учебной или тестовой конфигурации. Непосредственное знакомство с новым продуктом или сценарием помогает вам понять требования к его развертыванию, чтобы лучше спланировать его размещение в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="e9edc-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="e9edc-110">Кроме того, с помощью этих руководств можно создавать типичные среды для разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="e9edc-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e9edc-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="e9edc-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="e9edc-113">Базовая настройка</span><span class="sxs-lookup"><span data-stu-id="e9edc-113">Base configuration</span></span>

<span data-ttu-id="e9edc-p103">Вначале нужно создать тестовую среду для [Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/), включающую Office 365 E5, Enterprise Mobility + Security (EMS) E5 и Windows 10 Корпоративная. Ви можете создать два типа базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e9edc-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="e9edc-116">Используйте [простую базовую конфигурацию](lightweight-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный только в облачной среде, которая не включает каких-либо локальных компонентов.</span><span class="sxs-lookup"><span data-stu-id="e9edc-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="e9edc-117">Используйте [базовую конфигурацию "имитация предприятия"](simulated-ent-base-configuration-microsoft-365-enterprise.md), если вы хотите настроить и продемонстрировать функции и возможности Microsoft 365 корпоративный в гибридной облачной среде, которая использует локальные компоненты, такие как домен Windows Server Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="e9edc-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="e9edc-118">Идентификация</span><span class="sxs-lookup"><span data-stu-id="e9edc-118">Identity</span></span>

<span data-ttu-id="e9edc-119">Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e9edc-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="e9edc-120">Синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="e9edc-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="e9edc-121">Включение и проверка синхронизации службы каталогов на основе хэша пароля из контроллера домена Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="e9edc-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="e9edc-122">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="e9edc-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="e9edc-123">Включение и проверка сквозной проверки подлинности на контроллер домена Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="e9edc-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="e9edc-124">Простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="e9edc-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="e9edc-125">Обеспечение и проверка простого единого входа Azure AD с использованием контроллера домена Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="e9edc-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="e9edc-126">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="e9edc-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="e9edc-127">Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e9edc-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="e9edc-128">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="e9edc-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="e9edc-129">Блокировка учетных записей глобального администратора с помощью Office 365 Cloud App Security и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="e9edc-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="e9edc-130">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="e9edc-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="e9edc-131">Используйте функцию самостоятельного сброса пароля (SSPR) для сброса пароля.</span><span class="sxs-lookup"><span data-stu-id="e9edc-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="e9edc-132">Автоматическое лицензирование и членство в группах</span><span class="sxs-lookup"><span data-stu-id="e9edc-132">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="e9edc-133">Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.</span><span class="sxs-lookup"><span data-stu-id="e9edc-133">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="e9edc-134">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="e9edc-134">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="e9edc-135">Проверка текущих учетных записей пользователей на уязвимости.</span><span class="sxs-lookup"><span data-stu-id="e9edc-135">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="e9edc-136">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="e9edc-136">Mobile device management</span></span>

<span data-ttu-id="e9edc-137">Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e9edc-137">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="e9edc-138">Политики MAM</span><span class="sxs-lookup"><span data-stu-id="e9edc-138">MAM policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="e9edc-139">Создание групп пользователей и политик управления мобильными приложениями (MAM) для устройств с iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="e9edc-139">Create user groups and mobile application management (MAM) policies for iOS and Android devices.</span></span>
    
- [<span data-ttu-id="e9edc-140">Регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="e9edc-140">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="e9edc-141">Регистрация устройств с iOS или Android и удаленное управление ими.</span><span class="sxs-lookup"><span data-stu-id="e9edc-141">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="e9edc-142">Защита информации</span><span class="sxs-lookup"><span data-stu-id="e9edc-142">Information protection</span></span>

<span data-ttu-id="e9edc-143">Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e9edc-143">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="e9edc-144">Усиленная защита Office 365</span><span class="sxs-lookup"><span data-stu-id="e9edc-144">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="e9edc-145">Настройка параметров для усиления защиты Office 365 и изучение встроенных средств безопасности.</span><span class="sxs-lookup"><span data-stu-id="e9edc-145">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="e9edc-146">Классификация данных</span><span class="sxs-lookup"><span data-stu-id="e9edc-146">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="e9edc-147">Настройка и присвоение метки Office 365 документу на сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e9edc-147">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="e9edc-148">Управление привилегированным доступом для вашей тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e9edc-148">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="e9edc-149">Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9edc-149">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9edc-150">См. также</span><span class="sxs-lookup"><span data-stu-id="e9edc-150">See also</span></span>

[<span data-ttu-id="e9edc-151">Знакомство с Microsoft Cloud при помощи руководств по лаборатории тестирования для внедрения облачных технологий</span><span class="sxs-lookup"><span data-stu-id="e9edc-151">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="e9edc-152">Схема руководств по лаборатории тестирования для One Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="e9edc-152">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)
