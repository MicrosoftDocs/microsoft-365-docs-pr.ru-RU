---
title: Предварительные требования к удостоверениям и доступу к устройствам для сквозной проверки подлинности в тестовой среде Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для сквозной проверки подлинности.
ms.openlocfilehash: b8c9ebefacf81293b553aecf8ead0a387c18758b
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073029"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="3be9a-103">Предварительные требования к удостоверениям и доступу к устройствам для сквозной проверки подлинности в тестовой среде Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3be9a-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3be9a-104">[Конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) — это набор настроек и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD), включая Office 365 и Enterprise Mobility + Security (EMS) в Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3be9a-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="3be9a-105">В этой статье описано, как можно настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки сквозной проверки подлинности](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="3be9a-105">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="3be9a-106">Настройка этой тестовой среды состоит из восьми следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="3be9a-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="3be9a-107">Создание смоделированной организации с тестовой средой Microsoft 365 сквозной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3be9a-107">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="3be9a-108">Настройка простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="3be9a-108">Configure Azure AD single sign-on</span></span>
3.  <span data-ttu-id="3be9a-109">Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="3be9a-109">Configure named locations</span></span>
4.  <span data-ttu-id="3be9a-110">Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="3be9a-110">Configure password writeback</span></span>
5.  <span data-ttu-id="3be9a-111">Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="3be9a-111">Configure self-service password reset</span></span>
6.  <span data-ttu-id="3be9a-112">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3be9a-112">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="3be9a-113">Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="3be9a-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="3be9a-114">Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3be9a-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="3be9a-115">Этап 1. Создание смоделированной организации с тестовой средой Microsoft 365 сквозной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3be9a-115">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="3be9a-116">Выполните инструкции из статьи [Сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3be9a-116">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="3be9a-117">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="3be9a-117">Here is the resulting configuration.</span></span>

![Смоделированная организация с тестовой средой сквозной проверки подлинности](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="3be9a-119">Этап 2. Настройка простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="3be9a-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="3be9a-120">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для простого единого входа Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="3be9a-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="3be9a-121">Этап 3. Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="3be9a-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="3be9a-122">Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3be9a-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="3be9a-123">Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений.</span><span class="sxs-lookup"><span data-stu-id="3be9a-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="3be9a-124">Этап 4. Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="3be9a-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="3be9a-125">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="3be9a-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="3be9a-126">Этап 5. Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="3be9a-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="3be9a-127">Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="3be9a-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="3be9a-128">При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:</span><span class="sxs-lookup"><span data-stu-id="3be9a-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="3be9a-129">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="3be9a-129">User: %2</span></span>
- <span data-ttu-id="3be9a-130">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="3be9a-130">User Defined 3</span></span>
- <span data-ttu-id="3be9a-131">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="3be9a-131">User: %4</span></span>
- <span data-ttu-id="3be9a-132">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="3be9a-132">User 5</span></span>

<span data-ttu-id="3be9a-133">Проверьте сброс паролей только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="3be9a-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="3be9a-134">Этап 6. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="3be9a-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="3be9a-135">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="3be9a-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="3be9a-136">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="3be9a-136">User: %2</span></span>
- <span data-ttu-id="3be9a-137">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="3be9a-137">User Defined 3</span></span>
- <span data-ttu-id="3be9a-138">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="3be9a-138">User: %4</span></span>
- <span data-ttu-id="3be9a-139">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="3be9a-139">User 5</span></span>

<span data-ttu-id="3be9a-140">Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="3be9a-140">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="3be9a-141">Этап 7. Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="3be9a-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="3be9a-142">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="3be9a-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="3be9a-143">Этап 8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3be9a-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="3be9a-144">Для Exchange Online выполните [эти инструкции](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="3be9a-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="3be9a-145">Для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="3be9a-145">Skype for Business Online</span></span>

1. <span data-ttu-id="3be9a-146">Подключитесь к [Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3be9a-146">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="3be9a-147">Выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="3be9a-147">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="3be9a-148">Проверьте успешность изменения с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="3be9a-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="3be9a-149">Результатом является тестовая среда, соответствующая требованиям [предварительной настройки сквозной проверки подлинности](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="3be9a-149">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="3be9a-150">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="3be9a-150">Next step</span></span>

<span data-ttu-id="3be9a-151">См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="3be9a-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="3be9a-152">См. также</span><span class="sxs-lookup"><span data-stu-id="3be9a-152">See also</span></span>

[<span data-ttu-id="3be9a-153">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="3be9a-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="3be9a-154">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="3be9a-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="3be9a-155">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="3be9a-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3be9a-156">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="3be9a-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3be9a-157">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="3be9a-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

