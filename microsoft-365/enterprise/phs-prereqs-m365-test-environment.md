---
title: Предварительные требования к удостоверениям и доступу к устройствам для синхронизации хэша паролей в тестовой среде Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для проверки подлинности с синхронизацией хэша паролей.
ms.openlocfilehash: 125d8c6e1e954a05edd630c8f4d55848fa3314b3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066040"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="b8cb8-103">Предварительные требования к удостоверениям и доступу к устройствам для синхронизации хэша паролей в тестовой среде Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b8cb8-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="b8cb8-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b8cb8-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b8cb8-105">[Конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) — это набор настроек и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD), включая Office 365 и Enterprise Mobility + Security (EMS) в Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b8cb8-106">В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки Active Directory с синхронизацией хэша паролей](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="b8cb8-107">Настройка этой тестовой среды состоит из восьми следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="b8cb8-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="b8cb8-108">Создание тестовой среды смоделированной организации с синхронизацией хэша паролей</span><span class="sxs-lookup"><span data-stu-id="b8cb8-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="b8cb8-109">Настройка простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="b8cb8-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="b8cb8-110">Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="b8cb8-110">Configure named locations</span></span>
4.  <span data-ttu-id="b8cb8-111">Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="b8cb8-111">Configure password writeback</span></span>
5.  <span data-ttu-id="b8cb8-112">Настройка самостоятельного сброса пароля для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="b8cb8-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="b8cb8-113">Настройка многофакторной проверки подлинности для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="b8cb8-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="b8cb8-114">Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="b8cb8-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="b8cb8-115">Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b8cb8-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="b8cb8-116">Этап 1. Создание тестовой среды Microsoft 365 смоделированной организации с синхронизацией хэша паролей</span><span class="sxs-lookup"><span data-stu-id="b8cb8-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="b8cb8-117">Выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="b8cb8-118">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-118">Here is the resulting configuration.</span></span>

![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="b8cb8-120">Этап 2. Настройка простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="b8cb8-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="b8cb8-121">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для простого единого входа Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="b8cb8-122">Этап 3. Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="b8cb8-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="b8cb8-123">Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="b8cb8-124">Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="b8cb8-125">Этап 4. Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="b8cb8-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="b8cb8-126">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="b8cb8-127">Этап 5. Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="b8cb8-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="b8cb8-128">Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="b8cb8-129">При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:</span><span class="sxs-lookup"><span data-stu-id="b8cb8-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="b8cb8-130">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="b8cb8-130">User 2</span></span>
- <span data-ttu-id="b8cb8-131">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="b8cb8-131">User 3</span></span>
- <span data-ttu-id="b8cb8-132">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="b8cb8-132">User 4</span></span>
- <span data-ttu-id="b8cb8-133">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="b8cb8-133">User 5</span></span>

<span data-ttu-id="b8cb8-134">Проверьте сброс паролей только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="b8cb8-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="b8cb8-135">Этап 6. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b8cb8-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="b8cb8-136">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="b8cb8-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="b8cb8-137">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="b8cb8-137">User 2</span></span>
- <span data-ttu-id="b8cb8-138">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="b8cb8-138">User 3</span></span>
- <span data-ttu-id="b8cb8-139">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="b8cb8-139">User 4</span></span>
- <span data-ttu-id="b8cb8-140">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="b8cb8-140">User 5</span></span>

<span data-ttu-id="b8cb8-141">Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="b8cb8-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="b8cb8-142">Этап 7. Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="b8cb8-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="b8cb8-143">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="b8cb8-144">Этап 8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b8cb8-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="b8cb8-145">Для Exchange Online выполните [эти инструкции](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="b8cb8-146">Для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="b8cb8-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="b8cb8-147">Подключитесь к [Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b8cb8-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="b8cb8-148">Выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="b8cb8-149">Проверьте успешность изменения с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="b8cb8-150">Результатом является тестовая среда, соответствующая требованиям [предварительной настройки Active Directory с синхронизацией хэша паролей](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b8cb8-151">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="b8cb8-151">Next step</span></span>

<span data-ttu-id="b8cb8-152">См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="b8cb8-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8cb8-153">См. также</span><span class="sxs-lookup"><span data-stu-id="b8cb8-153">See also</span></span>

[<span data-ttu-id="b8cb8-154">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="b8cb8-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="b8cb8-155">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="b8cb8-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b8cb8-156">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b8cb8-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b8cb8-157">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b8cb8-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b8cb8-158">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="b8cb8-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
