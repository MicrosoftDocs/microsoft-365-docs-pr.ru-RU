---
title: Предварительные требования к удостоверениям и доступу к устройствам для сквозной проверки подлинности в тестовой среде Microsoft 365
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
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для сквозной проверки подлинности.
ms.openlocfilehash: 91b773b1ef2588490cf0434517a883ef447cd55d
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153860"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="945d1-103">Предварительные требования к удостоверениям и доступу к устройствам для сквозной проверки подлинности в тестовой среде Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="945d1-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="945d1-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="945d1-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="945d1-105">[Конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) — это набор настроек и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD), включая Office 365 и Enterprise Mobility + Security (EMS) в Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="945d1-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and Conditional Access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="945d1-106">В этой статье описано, как можно настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки сквозной проверки подлинности](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="945d1-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="945d1-107">Настройка этой тестовой среды состоит из восьми следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="945d1-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="945d1-108">Создание смоделированной организации с тестовой средой Microsoft 365 сквозной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="945d1-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="945d1-109">Настройка простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="945d1-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="945d1-110">Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="945d1-110">Configure named locations</span></span>
4.  <span data-ttu-id="945d1-111">Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="945d1-111">Configure password writeback</span></span>
5.  <span data-ttu-id="945d1-112">Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="945d1-112">Configure self-service password reset</span></span>
6.  <span data-ttu-id="945d1-113">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="945d1-113">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="945d1-114">Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="945d1-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="945d1-115">Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="945d1-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="945d1-116">Этап 1. Создание смоделированной организации с тестовой средой Microsoft 365 сквозной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="945d1-116">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="945d1-117">Выполните инструкции из статьи [Сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="945d1-117">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="945d1-118">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="945d1-118">Here is the resulting configuration.</span></span>

![Смоделированная организация с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="945d1-120">Этап 2. Настройка простого единого входа Azure AD</span><span class="sxs-lookup"><span data-stu-id="945d1-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="945d1-121">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для простого единого входа Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="945d1-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="945d1-122">Этап 3. Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="945d1-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="945d1-123">Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="945d1-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="945d1-124">Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений.</span><span class="sxs-lookup"><span data-stu-id="945d1-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="945d1-125">Этап 4. Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="945d1-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="945d1-126">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="945d1-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="945d1-127">Этап 5. Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="945d1-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="945d1-128">Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="945d1-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="945d1-129">При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:</span><span class="sxs-lookup"><span data-stu-id="945d1-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="945d1-130">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="945d1-130">User 2</span></span>
- <span data-ttu-id="945d1-131">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="945d1-131">User 3</span></span>
- <span data-ttu-id="945d1-132">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="945d1-132">User 4</span></span>
- <span data-ttu-id="945d1-133">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="945d1-133">User 5</span></span>

<span data-ttu-id="945d1-134">Проверьте сброс паролей только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="945d1-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="945d1-135">Этап 6. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="945d1-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="945d1-136">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="945d1-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="945d1-137">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="945d1-137">User 2</span></span>
- <span data-ttu-id="945d1-138">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="945d1-138">User 3</span></span>
- <span data-ttu-id="945d1-139">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="945d1-139">User 4</span></span>
- <span data-ttu-id="945d1-140">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="945d1-140">User 5</span></span>

<span data-ttu-id="945d1-141">Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="945d1-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="945d1-142">Этап 7. Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="945d1-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="945d1-143">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="945d1-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="945d1-144">Этап 8. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="945d1-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="945d1-145">Для Exchange Online выполните [эти инструкции](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="945d1-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="945d1-146">Для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="945d1-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="945d1-147">Подключитесь к [Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="945d1-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="945d1-148">Выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="945d1-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="945d1-149">Проверьте успешность изменения с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="945d1-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="945d1-150">Результатом является тестовая среда, соответствующая требованиям [предварительной настройки сквозной проверки подлинности](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="945d1-150">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="945d1-151">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="945d1-151">Next step</span></span>

<span data-ttu-id="945d1-152">См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="945d1-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="945d1-153">См. также</span><span class="sxs-lookup"><span data-stu-id="945d1-153">See also</span></span>

[<span data-ttu-id="945d1-154">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="945d1-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="945d1-155">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="945d1-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="945d1-156">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="945d1-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="945d1-157">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="945d1-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="945d1-158">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="945d1-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

