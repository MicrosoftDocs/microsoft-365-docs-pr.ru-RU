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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: С помощью этих руководств по лаборатории тестирования вы можете настраивать демонстрационные и экспериментальные среды, а также среды разработки и тестирования для Microsoft 365 на крупных предприятиях.
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487474"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="38eb9-103">Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях</span><span class="sxs-lookup"><span data-stu-id="38eb9-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="38eb9-104">*Это относится к Microsoft 365 для крупных предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="38eb9-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="38eb9-p101">Руководства по лаборатории тестирования помогают быстро знакомиться с продуктами Майкрософт. Они содержат инструкции по настройке упрощенных и наглядных тестовых сред. Эти среды можно использовать для демонстрации и настройки, а также создания сложных экспериментов на протяжении срока действия пробной или платной подписки.</span><span class="sxs-lookup"><span data-stu-id="38eb9-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="38eb9-p102">Руководствах TLG предназначены для модульной. Они построены друг на друга, чтобы создать несколько конфигураций, которые более точно соответствуют потребностям настройки обучения или тестирования. С помощью практических навыков вы сможете понять требования к развертыванию нового продукта или сценария, чтобы лучше спланировать их размещение в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="38eb9-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="38eb9-111">Кроме того, вы можете использовать руководствах TLG для создания репрезентативных сред для разработки и тестирования приложений, также известных как среды разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="38eb9-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="38eb9-113">Для наглядной карты со всеми статьями, приведенными в статье Microsoft 365 for Enterprise Test Lab Stack Stack, разверните приведенный ниже рисунок или перейдите в раздел [Microsoft 365 for Enterprise Test Lab Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="38eb9-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="38eb9-114">[![Руководства по лаборатории тестирования для Microsoft 365 на крупных предприятиях](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="38eb9-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="38eb9-115">Базовая настройка</span><span class="sxs-lookup"><span data-stu-id="38eb9-115">Base configuration</span></span>

<span data-ttu-id="38eb9-p103">Сначала создайте тестовую среду для [Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/). Можно создать два различных типа базовых конфигураций:</span><span class="sxs-lookup"><span data-stu-id="38eb9-p103">First, create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/). You can create two different types of base configurations:</span></span>

- <span data-ttu-id="38eb9-118">[Легковесная базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md) — используйте этот параметр, если вы хотите настроить и продемонстрировать Microsoft 365 для корпоративных функций и возможностей в облачной среде, которая не включает локальные компоненты.</span><span class="sxs-lookup"><span data-stu-id="38eb9-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="38eb9-119">[Конфигурация "имитация предприятия](simulated-ent-base-configuration-microsoft-365-enterprise.md) " — Используйте этот параметр, если вы хотите настроить и продемонстрировать Microsoft 365 для корпоративных функций и возможностей в гибридной облачной среде, в которой используются локальные компоненты, такие как домен доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="38eb9-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="38eb9-120">Кроме того, вы можете создавать тестовые среды для Office 365 E5, не добавляя лицензию Microsoft 365 E5 в пробную или рабочую тестовую среду.</span><span class="sxs-lookup"><span data-stu-id="38eb9-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="38eb9-121">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="38eb9-121">Identity</span></span>

<span data-ttu-id="38eb9-122">Функции и возможности, связанные с идентификацией, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="38eb9-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="38eb9-123">Синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="38eb9-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="38eb9-124">Включение и тестирование синхронизации службы каталогов на основе хэша пароля из контроллера домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="38eb9-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="38eb9-125">Сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="38eb9-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="38eb9-126">Включение и тестирование сквозной проверки подлинности на контроллере домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="38eb9-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="38eb9-127">Федеративная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="38eb9-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="38eb9-128">Включение и тестирование федеративной проверки подлинности на контроллере домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="38eb9-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="38eb9-129">Простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="38eb9-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="38eb9-130">Включить и протестировать единый вход в Azure AD с помощью контроллера домена AD DS.</span><span class="sxs-lookup"><span data-stu-id="38eb9-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="38eb9-131">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="38eb9-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="38eb9-132">Включение и тестирование многофакторной проверки подлинности с использованием смартфона для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="38eb9-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="38eb9-133">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="38eb9-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="38eb9-134">Блокирование учетных записей глобальных администраторов с помощью политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="38eb9-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="38eb9-135">Обратная запись пароля</span><span class="sxs-lookup"><span data-stu-id="38eb9-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="38eb9-136">Смена пароля учетной записи пользователя AD DS из Azure AD с помощью обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="38eb9-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="38eb9-137">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="38eb9-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="38eb9-138">Используйте самостоятельный сброс пароля, чтобы сбросить пароль.</span><span class="sxs-lookup"><span data-stu-id="38eb9-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="38eb9-139">Автоматическое лицензирование и членство в группах</span><span class="sxs-lookup"><span data-stu-id="38eb9-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="38eb9-140">Упрощение администрирования новых учетных записей с помощью автоматического лицензирования и динамического членства в группах.</span><span class="sxs-lookup"><span data-stu-id="38eb9-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="38eb9-141">Защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="38eb9-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="38eb9-142">Проверка текущих учетных записей пользователей на уязвимости.</span><span class="sxs-lookup"><span data-stu-id="38eb9-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="38eb9-143">Доступ к удостоверениям и устройствам</span><span class="sxs-lookup"><span data-stu-id="38eb9-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="38eb9-144">Создание среды для тестирования рекомендуемых конфигураций доступа к удостоверениям и устройствам и политик условного доступа.</span><span class="sxs-lookup"><span data-stu-id="38eb9-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="38eb9-145">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="38eb9-145">Mobile device management</span></span>

<span data-ttu-id="38eb9-146">Функции и возможности, связанные с управлением мобильными устройствами, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="38eb9-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="38eb9-147">Политики соответствия требованиям для устройств</span><span class="sxs-lookup"><span data-stu-id="38eb9-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="38eb9-148">Создайте группу пользователей и политику соответствия требованиям для устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="38eb9-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="38eb9-149">Регистрация устройств с iOS и Android</span><span class="sxs-lookup"><span data-stu-id="38eb9-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="38eb9-150">Регистрация устройств с iOS или Android и удаленное управление ими.</span><span class="sxs-lookup"><span data-stu-id="38eb9-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="38eb9-151">Защита информации</span><span class="sxs-lookup"><span data-stu-id="38eb9-151">Information protection</span></span>

<span data-ttu-id="38eb9-152">Функции и возможности, связанные с защитой информации, продемонстрированы в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="38eb9-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="38eb9-153">Повышенная безопасность в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="38eb9-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="38eb9-154">Настройка параметров для усиления защиты Microsoft 365 и изучение встроенных средств безопасности.</span><span class="sxs-lookup"><span data-stu-id="38eb9-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="38eb9-155">Классификация данных</span><span class="sxs-lookup"><span data-stu-id="38eb9-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="38eb9-156">Настройка меток и присвоение их документу на сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38eb9-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="38eb9-157">Управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="38eb9-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="38eb9-158">Настройка управления привилегированным доступом для своевременного доступа к задачам, требующим привилегий и разрешений повышенного уровня, в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="38eb9-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>
