---
title: Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для облачной проверки подлинности.
ms.openlocfilehash: a8025a2543a53a229be13d19c246165fe88ad433
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685788"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="0d40e-103">Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d40e-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="0d40e-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="0d40e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="0d40e-105">[Конфигурации доступа для удостоверений и устройств](microsoft-365-policies-configurations.md) — это набор конфигураций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0d40e-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="0d40e-106">В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки облачной среды](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="0d40e-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="0d40e-107">Настройка этой тестовой среды состоит из семи следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="0d40e-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="0d40e-108">Создание простой тестовой среды</span><span class="sxs-lookup"><span data-stu-id="0d40e-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="0d40e-109">Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="0d40e-109">Configure named locations</span></span>
3.  <span data-ttu-id="0d40e-110">Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="0d40e-110">Configure password writeback</span></span>
4.  <span data-ttu-id="0d40e-111">Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="0d40e-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="0d40e-112">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0d40e-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="0d40e-113">Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="0d40e-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="0d40e-114">Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0d40e-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="0d40e-115">Этап 1. Создание упрощенной тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d40e-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="0d40e-116">Следуйте инструкциям в статье [Простая базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0d40e-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="0d40e-117">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="0d40e-117">Here is the resulting configuration.</span></span>

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="0d40e-119">Этап 2. Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="0d40e-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="0d40e-120">Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0d40e-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="0d40e-121">Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений.</span><span class="sxs-lookup"><span data-stu-id="0d40e-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="0d40e-122">Этап 3. Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="0d40e-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="0d40e-123">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="0d40e-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="0d40e-124">Этап 4. Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="0d40e-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="0d40e-125">Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="0d40e-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="0d40e-126">При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:</span><span class="sxs-lookup"><span data-stu-id="0d40e-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="0d40e-127">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="0d40e-127">User 2</span></span>
- <span data-ttu-id="0d40e-128">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="0d40e-128">User 3</span></span>
- <span data-ttu-id="0d40e-129">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="0d40e-129">User 4</span></span>
- <span data-ttu-id="0d40e-130">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="0d40e-130">User 5</span></span>

<span data-ttu-id="0d40e-131">Проверьте сброс паролей только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="0d40e-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="0d40e-132">Этап 5. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0d40e-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="0d40e-133">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="0d40e-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="0d40e-134">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="0d40e-134">User 2</span></span>
- <span data-ttu-id="0d40e-135">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="0d40e-135">User 3</span></span>
- <span data-ttu-id="0d40e-136">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="0d40e-136">User 4</span></span>
- <span data-ttu-id="0d40e-137">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="0d40e-137">User 5</span></span>

<span data-ttu-id="0d40e-138">Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="0d40e-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="0d40e-139">Этап 6. Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="0d40e-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="0d40e-140">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="0d40e-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="0d40e-141">Этап 7. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0d40e-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="0d40e-142">Для Exchange Online выполните [эти инструкции](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="0d40e-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="0d40e-143">Для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="0d40e-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="0d40e-144">Подключитесь к [Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0d40e-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="0d40e-145">Выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="0d40e-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="0d40e-146">Проверьте успешность изменения с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="0d40e-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="0d40e-147">Результатом является тестовая среда, соответствующая требованиям [предварительной настройки облачной среды](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="0d40e-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="0d40e-148">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="0d40e-148">Next step</span></span>

<span data-ttu-id="0d40e-149">См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="0d40e-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d40e-150">См. также</span><span class="sxs-lookup"><span data-stu-id="0d40e-150">See also</span></span>

[<span data-ttu-id="0d40e-151">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="0d40e-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="0d40e-152">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="0d40e-152">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="0d40e-153">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="0d40e-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0d40e-154">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="0d40e-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0d40e-155">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="0d40e-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
